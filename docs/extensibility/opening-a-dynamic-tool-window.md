---
title: "動的なツール ウィンドウを開く |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tool windows, dynamic
ms.assetid: 21547ba7-6e81-44df-9277-265bf34f877a
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 588badc75a604df65949c99fa16f84ad4e9c9175
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="opening-a-dynamic-tool-window"></a>動的なツール ウィンドウを開く
ツール ウィンドウは通常、対応するキーボード ショートカットやメニューのコマンドから開きます。 ときに、ただし、必要がありますツール ウィンドウを特定の UI コンテキストが適用され、UI コンテキストが適用されなくなったときに終了するたびに開きます。 上記のようなツール ウィンドウと呼びます*動的*または*自動表示*です。  
  
> [!NOTE]
>  定義済みの UI コンテキストの一覧は、次を参照してください。<xref:Microsoft.VisualStudio.VSConstants.UICONTEXT>です。 には  
  
 場合は、起動時に動的なツール ウィンドウを開くと、作成が失敗する可能性が、実装する必要があります、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx>インターフェイスし、エラーの条件をテスト、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx.QueryShowTool%2A>メソッドです。 シェルの起動時に開く必要がある動的なツール ウィンドウがあることを知るためには、追加する必要があります、`SupportsDynamicToolOwner`値 (1 に設定)、パッケージを登録します。 この値は、標準の一部ではない<xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>ので、それを追加するカスタム属性を作成する必要があります。 カスタム属性に関する詳細については、次を参照してください。[カスタム登録属性を使用して拡張機能を登録する](../extensibility/registering-and-unregistering-vspackages.md#using-a-custom-registration-attribute-to-register-an-extension)です。  
  
 使用して<xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A>ツール ウィンドウを開きます。 必要に応じて、ツール ウィンドウが作成されます。  
  
> [!NOTE]
>  動的なツール ウィンドウは、ユーザーが終了することができます。 ユーザーがツール ウィンドウを開くことができますので、メニュー コマンドを作成する場合は、無効になっていますそれ以外の場合とツール ウィンドウに表示される同じ UI コンテキストで、メニュー コマンドが有効にする必要があります。  
  
### <a name="to-open-a-dynamic-tool-window"></a>動的なツール ウィンドウを開く  
  
1.  という名前の VSIX プロジェクトを作成する**DynamicToolWindow**という名前のツール ウィンドウの項目テンプレートを追加および**DynamicWindowPane.cs**です。 詳細については、次を参照してください。[ツール ウィンドウで、拡張機能の作成](../extensibility/creating-an-extension-with-a-tool-window.md)です。  
  
2.  DynamicWindowPanePackage.cs ファイルで DynamicWindowPanePackage 宣言を検索します。 追加、<xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute>と T:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute 属性ツール ウィンドウを登録します。  
  
    ```vb  
    [[ProvideToolWindow(typeof(DynamicWindowPane)]  
    [ProvideToolWindowVisibility(typeof(DynamicWindowPane), VSConstants.UICONTEXT.SolutionExists_string)]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [ProvideToolWindow(typeof(DynamicToolWindow.DynamicWindowPane))]  
    [Guid(DynamicWindowPanePackageGuids.PackageGuidString)]  
    public sealed class DynamicWindowPanePackage : Package  
    {. . .}  
    ```  
  
     これにより、Visual Studio を閉じて、再び開くときに永続化されていません、一時的なウィンドウとして DynamicWindowPane をという名前のツール ウィンドウが登録されます。 DynamicWindowPane が開かれるたびに<xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_string>が適用され、それ以外の場合に終了します。  
  
3.  プロジェクトをビルドし、デバッグを開始します。 実験用インスタンスが表示されます。 ツール ウィンドウは表示されません。  
  
4.  実験用インスタンスで、プロジェクトを開きます。 ツール ウィンドウが表示されます。