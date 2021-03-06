---
title: "ビルド システムのカスタマイズ | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 6958B102-8527-4B40-BC65-3505DB63F9D3
ms.openlocfilehash: 2d17a952c58e5ef7e593ee7aeb1980e09a376800
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="customizing-the-build-system"></a>ビルド システムのカスタマイズ

MSbuild は Microsoft が開発したビルド エンジンです。主に .NET アプリケーションのビルドを可能にします。 Mono フレームワークはまた、Microsoft のビルド エンジンを独自に実装しています。それが **xbuild** です。 ただし、xbuild は廃止となり、すべてのオペレーティング システムで MSBuild が使用されています。

**MSbuild** は、Visual Studio for Mac のビルド システムとして主に使用されます。 

MSBuild は、ソース ファイルなど、一連の入力を受け取ることで動作し、入力を実行可能ファイルなどの出力に変換し、コンパイラのようなツールを呼び出すことでその出力を実行します。 


## <a name="msbuild-file"></a>MSBuild ファイル

MSBuild は、プロジェクト ファイルと呼ばれる XML ファイルを使用します。このファイルはプロジェクトの一部である*アイテム* (イメージ リソースなど) とプロジェクトのビルドに必要な*プロパティ*を定義します。 このプロジェクト ファイルのファイル拡張子は常に `proj` で終わります。たとえば、C# プロジェクトの場合、`.csproj` になります。 

### <a name="viewing-the-msbuild-file"></a>MSBuild ファイルを表示する
このファイルを見つけるには、プロジェクト名を右クリックし、**[Finder に表示]** を選択します。 下の画像のように、プロジェクトに関連するすべてのファイルとフォルダーが表示されます。`.csproj` ファイルも表示されます。

![](media/customizing-build-system-image1.png)

Visual Studio for Mac では、新しいタブに `.csproj` を表示することもできます。プロジェクト名を右クリックし、**[ツール]、[ファイルの編集]** の順に選択します。

![](media/customizing-build-system-image2.png)

### <a name="composition-of-the-msbuild-file"></a>MSBuild ファイルの構成

すべての MSBuild ファイルに、下の画像のように、必須のルート `Project` 要素が含まれています。

```
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="14.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
</Project>
```

通常、プロジェクトは `.targets` ファイルもインポートします。このファイルには、さまざまなファイルを処理し、ビルドする方法を説明したルールがたくさん含まれています。 これは通常、`proj` ファイルの下のほうに表示されます。C# プロジェクトの場合、次の画像のようになります。

```
<Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />
```

ターゲット ファイルは別の MSBuild ファイルです。 このファイルに含まれる MSBuild コードは、複数のプロジェクトで再利用できます。 たとえば、`MSBuildBinPath` プロパティ (または変数) で表されるディレクトリにある `Microsoft.CSharp.targets` ファイルには、C# ソース ファイルから C# アセンブリをビルドするためのロジックが含まれています。

### <a name="items-and-properties"></a>項目とプロパティ

MSBuild には、*項目*と*プロパティ*という 2 つの基本データ型があります。これについて以下で説明します。

#### <a name="properties"></a>プロパティ

プロパティは、コンパイラ オプションなど、コンパイル設定を格納するための鍵と値のペアです。

プロパティは PropertyGroup を利用して設定されます。また、プロパティには、任意の数の PropertiesGroups を追加できます (PropertiesGroups にはさらに任意の数のプロパティを追加できます)。 

たとえば、簡単なコンソール アプリケーションの PropertyGroup は次のようになります。

```
<PropertyGroup>
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
        <Platform Condition=" '$(Platform)' == '' ">x86</Platform>
        <ProjectGuid>{E248730E-1393-43CC-9183-FFA42F63BE81}</ProjectGuid>
        <OutputType>Exe</OutputType>
        <RootNamespace>refactoring</RootNamespace>
        <AssemblyName>refactoring</AssemblyName>
        <TargetFrameworkVersion>v4.5</TargetFrameworkVersion>
    </PropertyGroup>
```

プロパティは `$()` 構文を利用して式から参照できます。 たとえば、`$(Foo)` は `Foo` プロパティの値として評価されます。 プロパティが設定されていない場合、エラーなしで、空の文字列として評価されます。

#### <a name="items"></a>項目

項目を利用することで、ビルド システムへの入力をリストやセットとして扱うことができます。項目は一般的にファイルを表します。 項目にはそれぞれ、項目の*種類*と*仕様*が与えられ、任意で*メタデータ*が指定されます。 MSBuild が個々の項目に対して機能することはありません。項目*セット*と呼ばれる、特定の種類のすべての項目に対して機能します。

項目は、`ItemGroup` を宣言することで作成されます。 任意の数の項目を含めた ItemGroups をさらに任意の数だけ作成できます。 

たとえば、下のコード スニペットでは、iOS の起動画面が作成されます。 これは `BundleResource` 型です。画像へのパスとして仕様が指定されています。

```
 <ItemGroup>
    <BundleResource Include="Resources\Default-568h%402x.png" />
    <BundleResource Include="Resources\Default%402x.png" />
    <BundleResource Include="Resources\Default.png" />
    <BundleResource Include="Resources\Default-Portrait.png" />
    <BundleResource Include="Resources\Default-Portrait%402x.png" />
    <BundleResource Include="Resources\Default-Landscape%402x.png" />
  </ItemGroup>
 ```
 
 項目セットは、`@()` 構文を利用して式から参照できます。 たとえば、`@(BundleResource)` は BundleResource 項目セットとして評価されます。すべての BundleResource 項目を意味します。 この種類の項目がない場合、エラーなしで空になります。

## <a name="resources-for-learning-msbuild"></a>MSBuild の学習リソース

次のリソースで MSBuild についてさらに詳しく学習できます。

* [MSDN - 概要](https://msdn.microsoft.com/library/dd393574.aspx)
* [MSDN - 概念](https://msdn.microsoft.com/library/dd637714.aspx)


