---
title: "Visual Studio for Mac のコンパイルとビルド | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: 9005cf64f4b72f39923d6525e78de745d79c3953
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>Visual Studio for Mac のコンパイルとビルド

Visual Studio for Mac は、プロジェクトの開発中、アプリケーションをビルドし、アセンブリを作成するために使用できます。 型の不一致やその他のコンパイル時エラーが見つかるように、コードは早い段階で頻繁にコンパイルし、ビルドすることが重要です。

## <a name="choosing-a-build-method"></a>ビルド方法の選択:

### <a name="using-the-ide"></a>IDE の使用

Visual Studio for Mac を使用すると、ビルドをすぐに作成し、実行できます。また、ビルド機能を制御できます。 Visual Studio for Mac では、基礎ビルド システムとして MSBuild が使用されます。

IDE で作成されたすべてのプロジェクトとソリューションに既定のビルド構成が与えられます。この構成がビルドのコンテキストを定義します。 構成は編集可能です。独自の構成を作成するともできます。 構成を作成したり、変更したりすると、プロジェクト ファイルが自動的に更新されます。それが MSBuild で使用され、プロジェクトがビルドされます。  

IDE でプロジェクトやソリューションをビルドする方法については、「[プロジェクトとソリューションのビルドおよびクリーン](~/building-and-cleaning-projects-and-solutions.md)」ガイドを参照してください。

Visual Studio for Mac は以下にも使用できます。

* 出力パスを変更します。 これはプロジェクトのオプションで編集します。

    ![出力パスの変更](media/compiling-and-building-image4.png)

* ビルド出力の詳細度を変更します。

    ![ビルドの詳細度の変更](media/compiling-and-building-image5.png)

* ビルドまたはクリーンの前後に、またはビルドまたはクリーンの最中にカスタム コマンドを追加します。

    ![カスタム コマンドを追加する](media/compiling-and-building-image6.png)

### <a name="building-from-command-line"></a>コマンド ラインからビルドする

MSBuild Build Engine を使用し、コマンド ラインからアプリケーションをビルドできます。

MSBuild の使用方法については、[MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild) コンテンツをご覧ください。

### <a name="using-visual-studio-team-services"></a>Visual Studio Team Services を使用する

* [Xamarin アプリをビルドする](https://www.visualstudio.com/docs/build/apps/mobile/xamarin)
* [Xamarin との継続的な統合](https://developer.xamarin.com/guides/cross-platform/ci/)