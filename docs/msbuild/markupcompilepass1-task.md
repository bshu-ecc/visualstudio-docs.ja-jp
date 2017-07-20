---
title: "MarkupCompilePass1 タスク | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- converting XAML to binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], parameters
- converting XAML projects to compiled binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], converting XAML to binary format
ms.assetid: 693d6945-fd6f-4698-8f64-9dfcb71052d3
caps.latest.revision: 8
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 79460291e91f0659df0a4241e17616e55187a0e2
ms.openlocfilehash: d4cb33cd46ab45c580e70ce7e590960ed4fd75a9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/22/2017

---
# <a name="markupcompilepass1-task"></a>MarkupCompilePass1 タスク
<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> タスクは、ローカライズできない [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] プロジェクト ファイルをコンパイル済みバイナリ形式に変換します。  
  
## <a name="task-parameters"></a>タスク パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`AllGeneratedFiles`|省略可能な **ITaskItem[]** 型の出力パラメーターです。<br /><br /> <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> タスクによって生成されるファイルの完全な一覧が含まれます。|  
|`AlwaysCompileMarkupFilesInSeparateDomain`|省略可能な **Boolean** 型のパラメーターです。<br /><br /> タスクを別の <xref:System.AppDomain> で実行するかどうかを指定します。 このパラメーターが **false** を返す場合、タスクは [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] と同じ <xref:System.AppDomain> 内で、より高速に実行されます。 このパラメーターが **true** を返す場合、タスクは [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] から分離された 2 番目の <xref:System.AppDomain> 内で実行され、動作はより低速になります。|  
|`ApplicationMarkup`|省略可能な **ITaskItem[]** パラメーターです。<br /><br /> アプリケーション定義 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルの名前を指定します。|  
|`AssembliesGeneratedDuringBuild`|省略可能な **String[]** 型のパラメーターです。<br /><br /> ビルド処理時に変更されるアセンブリへの参照を指定します。 たとえば、[!INCLUDE[TLA#tla_visualstu2005](../msbuild/includes/tlasharptla_visualstu2005_md.md)] ソリューションには、別のプロジェクトのコンパイル済み出力を参照するプロジェクトが含まれていることがあります。 この場合、別のプロジェクトのコンパイル済み出力を **AssembliesGeneratedDuringBuild** パラメーターに追加できます。<br /><br /> 注: **AssembliesGeneratedDuringBuild** パラメーターは、ビルド ソリューションによって生成されるアセンブリの完全なセットへの参照を含んでいる必要があります。|  
|`AssemblyName`|必須の **String** 型のパラメーターです。<br /><br /> プロジェクトのために生成されるアセンブリの短い名前を指定します。 たとえば、プロジェクトが **WinExeAssembly.exe** という名前の [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] 実行可能ファイルを生成する場合、**AssemblyName** パラメーターの値は **WinExeAssembly** になります。|  
|`AssemblyPublicKeyToken`|省略可能な **String** 型のパラメーターです。<br /><br /> アセンブリの公開キー トークンを指定します。|  
|`AssemblyVersion`|省略可能な **String** 型のパラメーターです。<br /><br /> アセンブリのバージョン番号を指定します。|  
|`ContentFiles`|省略可能な **ITaskItem[]** パラメーターです。<br /><br /> 圧縮しないコンテンツ ファイルの一覧を指定します。|  
|`DefineConstants`|省略可能な **String** 型のパラメーターです。<br /><br /> **DefineConstants** の現在の値を保持するように指定します。 これはターゲット アセンブリの生成に影響します。このパラメーターが変更されると、ターゲット アセンブリ内のパブリック API が変更される可能性があり、ローカル型を参照する [!INCLUDE[TLA2#tla_titlexaml](../msbuild/includes/tla2sharptla_titlexaml_md.md)] ファイルのコンパイルが影響を受けることがあります。|  
|`ExtraBuildControlFiles`|省略可能な **ITaskItem[]** パラメーターです。<br /><br /> <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> タスクを再実行した場合に、リビルドがトリガーされるかどうかを制御するファイルの一覧を指定します。これらのファイルのいずれかが変更されると、リビルドがトリガーされます。|  
|`GeneratedBamlFiles`|省略可能な **ITaskItem[]** 型の出力パラメーターです。<br /><br /> [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] バイナリ形式で生成されたファイルの一覧を含みます。|  
|`GeneratedCodeFiles`|省略可能な **ITaskItem[]** 型の出力パラメーターです。<br /><br /> 生成されるマネージ コード ファイルの一覧を含みます。|  
|`GeneratedLocalizationFiles`|省略可能な **ITaskItem[]** 型の出力パラメーターです。<br /><br /> ローカライズ可能な各 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルに対して生成されたローカリゼーション ファイルの一覧を含みます。|  
|`HostInBrowser`|省略可能な **String** 型のパラメーターです。<br /><br /> 生成されるアセンブリが [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] であるかどうかを指定します。 有効なオプションは、**true** および **false** です。 **true** の場合は、ブラウザーのホスト処理をサポートするコードが生成されます。|  
|`KnownReferencePaths`|省略可能な **String[]** 型のパラメーターです。<br /><br /> ビルド処理時に変更されないアセンブリへの参照を指定します。 [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)]、[!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] インストール ディレクトリなどにあるアセンブリが含まれます。|  
|`Language`|必須の **String** 型のパラメーターです。<br /><br /> コンパイラがサポートするマネージ言語を指定します。 有効なオプションは **C#**、**VB**、**JScript**、**C++** です。|  
|`LanguageSourceExtension`|省略可能な **String** 型のパラメーターです。<br /><br /> 生成されるマネージ コード ファイルの拡張子に追加される拡張子を指定します。<br /><br /> `<Filename>.g<LanguageSourceExtension>`<br /><br /> **LanguageSourceExtension** パラメーターが特定の値に設定されていない場合、言語に応じた既定のソース ファイル名拡張子が使用されます。つまり、[!INCLUDE[TLA#tla_visualb](../msbuild/includes/tlasharptla_visualb_md.md)] では **.vb** になり、[!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)] では **.csharp** になります。|  
|`LocalizationDirectivesToLocFile`|省略可能な **String** 型のパラメーターです。<br /><br /> 各ソース [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルのローカリゼーション情報を生成する方法を指定します。 有効なオプションは、**None**、**CommentsOnly**、および **All** です。|  
|`OutputPath`|必須の **String** 型のパラメーターです。<br /><br /> 生成されるマネージ コード ファイルおよび [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] バイナリ形式ファイルの出力先ディレクトリを指定します。|  
|`OutputType`|必須の **String** 型のパラメーターです。<br /><br /> プロジェクトで生成されるアセンブリの型を指定します。 有効なオプションは、**winexe**、**exe**、**library**、および **netmodule** です。|  
|`PageMarkup`|省略可能な **ITaskItem[]** パラメーターです。<br /><br /> 処理する [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルの一覧を指定します。|  
|`References`|省略可能な **ITaskItem[]** パラメーターです。<br /><br /> [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイル内で使用される型を含む、ファイルからアセンブリへの参照の一覧を指定します。|  
|`RequirePass2ForMainAssembly`|省略可能な **Boolean** 型の出力パラメーターです。<br /><br /> メイン アセンブリに埋め込まれるローカル型を参照する、ローカライズできない [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルがプロジェクトに含まれているかどうかを示します。|  
|`RequirePass2ForSatelliteAssembly`|省略可能な **Boolean** 型の出力パラメーターです。<br /><br /> メイン アセンブリに埋め込まれるローカル型を参照する、ローカライズ可能な [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルがプロジェクトに含まれているかどうかを示します。|  
|`RootNamespace`|省略可能な **String** 型のパラメーターです。<br /><br /> プロジェクト内部にあるクラスのルート名前空間を指定します。 **RootNamespace** は、対応する [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルが `x:Class` 属性を含まない場合に、生成されるマネージ コード ファイルの既定の名前空間としても使用されます。|  
|`SourceCodeFiles`|省略可能な **ITaskItem[]** パラメーターです。<br /><br /> 現在のプロジェクトのコード ファイルの一覧を指定します。 このリストには、生成される言語固有のマネージ コード ファイルは含まれません。|  
|`UICulture`|省略可能な **String** 型のパラメーターです。<br /><br /> 生成される [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] バイナリ形式ファイルが埋め込まれる UI カルチャのサテライト アセンブリを指定します。 **UICulture** が設定されない場合、生成される [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] バイナリ形式ファイルは、メイン アセンブリに埋め込まれます。|  
|`XAMLDebuggingInformation`|省略可能な **Boolean** 型のパラメーターです。<br /><br /> **true** の場合、デバッグを支援するための診断情報が生成され、コンパイルされた [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 内に追加されます。|  
  
## <a name="remarks"></a>コメント  
 <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> タスクは、通常、[!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] をバイナリ形式にコンパイルしてコード ファイルを生成します。 同じプロジェクト内で定義される型への参照が [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルに含まれている場合、**MarkupCompilePass1** は、バイナリ形式へのコンパイルを 2 番目のマークアップ コンパイル パス (**MarkupCompilePass2**) まで延期します。 このようなファイルでは、参照しているローカル定義の型がコンパイルされるまで待つ必要があるため、コンパイルを延期する必要があります。 ただし、[!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルに `x:Class` 属性がある場合、<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> はこのファイルの言語固有のコード ファイルを生成します。  
  
 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルに `x:Uid` 属性を使用する要素が含まれている場合、そのファイルはローカライズ可能です。  
  
```xml  
<Page x:Class="WPFMSBuildSample.Page1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    x:Uid="Page1Uid"  
    >  
  ...  
</Page>  
```  
  
 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルは、`clr-namespace` 値を使用して現在のプロジェクトの名前空間を参照する [!INCLUDE[TLA#tla_xml](../msbuild/includes/tlasharptla_xml_md.md)] 名前空間を宣言している場合、ローカルに定義された型を参照します。  
  
```xml  
<Page x:Class="WPFMSBuildSample.Page1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:localNamespace="clr-namespace:WPFMSBuildSample"  
    >  
    <Grid>  
      <Grid.Resources>  
        <localNameSpace:LocalType x:Key="localType" />  
      </Grid.Resources>  
      ...  
    </Grid>  
</Page>  
```  
  
 いずれかの [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルがローカライズ可能であるか、またはローカルに定義された型を参照している場合は、2 番目のマークアップ コンパイル パスが必要です。このパスでは、[GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md) を実行し、次に [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md) を実行する必要があります。  
  
## <a name="example"></a>例  
 3 つの `Page`[!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ファイルをバイナリ形式ファイルに変換する方法を次の例に示します。 `Page1` には、`Class1` という型への参照が含まれます。この型はプロジェクトのルート名前空間内にあるため、このマークアップ コンパイル パスではバイナリ形式ファイルに変換されません。 代わりに、[GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md) が実行され、次に [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md) が実行されます。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass1"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MarkupCompilePass1Task">  
    <MarkupCompilePass1   
      AssemblyName="WPFMSBuildSample"  
      Language="C#"  
      OutputType="WinExe"  
      OutputPath="obj\Debug\"  
      ApplicationMarkup="App.xaml"  
      PageMarkup="Page1.xaml;Page2.xaml;Page3.xaml"  
      SourceCodeFiles="Class1.cs"  
      References="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>関連項目  
 [WPF MSBuild リファレンス](../msbuild/wpf-msbuild-reference.md)   
 [Task Reference (タスク リファレンス)](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild リファレンス](../msbuild/msbuild-reference.md)   
 [Task Reference (タスク リファレンス)](../msbuild/msbuild-task-reference.md)   
 [WPF アプリケーション (WPF) のビルド](http://msdn.microsoft.com/Library/a58696fd-bdad-4b55-9759-136dfdf8b91c)   
 [WPF XAML ブラウザー アプリケーションの概要](http://msdn.microsoft.com/Library/3a7a86a8-75d5-4898-96b9-73da151e5e16)