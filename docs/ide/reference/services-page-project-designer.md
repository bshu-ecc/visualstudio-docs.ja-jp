---
title: "[サービス] ページ (プロジェクト デザイナー) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.ProjectPropertiesServices
helpviewer_keywords:
- Services page in Project Designer
- Project Designer, Services page
ms.assetid: 6dd9e0fa-acba-4d7d-b081-705b0fc86ff5
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0800884a03544aec822d31cf64fd47a4f63f3e07
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="services-page-project-designer"></a>[サービス] ページ (プロジェクト デザイナー)
クライアント アプリケーション サービスにより、Windows フォーム アプリケーションおよび Windows Presentation Foundation (WPF) アプリケーションから [!INCLUDE[ajax_current_short](../../ide/reference/includes/ajax_current_short_md.md)] ログイン サービス、ロール サービス、プロファイル サービスに簡単にアクセスできます。 クライアント アプリケーション サービスは、**プロジェクト デザイナー**の **[サービス]** ページで有効にし、構成することができます。  
  
 クライアント アプリケーション サービスを使用すると、中央のサーバーを使用してユーザーを認証し、各ユーザーの割り当てられたロール (複数可) を判断し、ネットワーク経由で共有できるユーザーごとのアプリケーション設定を保存できます。 詳細については、「[クライアント アプリケーション サービス](/dotnet/framework/common-client-technologies/client-application-services)」を参照してください。  
  
 この **[サービス]** ページにアクセスするには、**ソリューション エクスプローラー**でプロジェクト ノードを選択し、**[プロジェクト]** メニューの **[プロパティ**] をクリックします。 **プロジェクト デザイナー** が表示されたら、**[サービス]** タブをクリックします。  
  
> [!NOTE]
>  クライアント アプリケーション サービスには完全版の .NET Framework が必要です。クライアント アプリケーション サービスは、.NET Framework Client Profile ではサポートされません。 **[クライアント アプリケーション サービスを有効にする]** チェック ボックスが無効になっている場合、**[ターゲット フレームワーク]** が .NET Framework 3.5 以降に設定されていることを確認します。 C# で **[ターゲット フレームワーク]** の設定を表示するには、プロジェクト デザイナーを開き、**[アプリケーション]** ページをクリックします。 Visual Basic で **[ターゲット フレームワーク]** の設定を表示するには、プロジェクト デザイナーを開き、**[コンパイル]** ページをクリックして、**[詳細コンパイル オプション]** をクリックします。  
  
## <a name="task-list"></a>タスク一覧  
 [方法 : クライアント アプリケーション サービスを構成する](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **構成**  
 このコントロールは、このページでは編集できません。 このコントロールの詳細については、「[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)」または「[[ビルド] ページ (プロジェクト デザイナー) (C#)](../../ide/reference/build-page-project-designer-csharp.md)」を参照してください。  
  
 **プラットフォーム**  
 このコントロールは、このページでは編集できません。 このコントロールの詳細については、「[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)」または「[[ビルド] ページ (プロジェクト デザイナー) (C#)](../../ide/reference/build-page-project-designer-csharp.md)」を参照してください。  
  
 **クライアント アプリケーション サービスを有効にする**  
 選択すると、クライアント アプリケーション サービスが有効になります。 クライアント アプリケーション サービスを使用するには、**[サービス]** ページでサービスの場所を指定する必要があります。  
  
 **Windows 認証の使用**  
 認証プロバイダーが Windows ベースの認証、つまり Windows オペレーティング システムによって付与された ID を使用することを示します。  
  
 **フォーム認証を使用する**  
 認証プロバイダーがフォーム認証を使用することを示します。 つまり、アプリケーションがログインのユーザー インターフェイスを提供する必要があります。 詳細については、「[方法: クライアント アプリケーション サービスでユーザーのログインを実装する](/dotnet/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services)」を参照してください。  
  
 **認証サービスの場所**  
 フォーム認証でのみ使用します。 認証サービスの場所を指定します。  
  
 **省略可能: 資格情報プロバイダー**  
 フォーム認証でのみ使用します。 アプリケーションが `static`<xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> メソッドを呼び出し、パラメーターに空の文字列または `null` を渡したときに、認証サービスでログイン ダイアログ ボックスを表示するために使用する <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 実装を示します。 このボックスを空白のままにした場合は、<xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> メソッドに有効なユーザー名とパスワードを渡す必要があります。 アセンブリ修飾型名として資格情報プロバイダーを指定する必要があります。 詳細については、「<xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>」および「[アセンブリ名](/dotnet/framework/app-domains/assembly-names)」を参照してください。 最も単純な形式では、アセンブリ修飾型名は、次のようになります。`MyNamespace.MyLoginClass, MyAssembly`  
  
 **ロール サービスの場所**  
 ロール サービスの場所を指定します。  
  
 **Web 設定サービスの場所**  
 プロファイル (Web 設定) サービスの場所を指定します。  
  
 **詳細設定**  
 既定の動作をオーバーライドすることができる [[サービスの詳細設定] ダイアログ ボックス](../../ide/reference/advanced-settings-for-services-dialog-box.md)を開きます。 たとえば、このダイアログ ボックスを使用すると、ローカル ファイル システムを使用する代わりに、オフラインのストレージにデータベースを指定できます。 詳細については、「[[サービスの詳細設定] ダイアログ ボックス](../../ide/reference/advanced-settings-for-services-dialog-box.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [クライアント アプリケーション サービス](/dotnet/framework/common-client-technologies/client-application-services)   
 [[サービスの詳細設定] ダイアログ ボックス](../../ide/reference/advanced-settings-for-services-dialog-box.md)   
 [方法 : クライアント アプリケーション サービスを構成する](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)   
 [[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [[ビルド] ページ (プロジェクト デザイナー) (C#)](../../ide/reference/build-page-project-designer-csharp.md)   
