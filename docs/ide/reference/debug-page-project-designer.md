---
title: "[デバッグ] ページ (プロジェクト デザイナー) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.ProjectPropertiesDebug
helpviewer_keywords:
- Project Designer, Debug page
- Debug page in Project Designer
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39b19b6e418203a33c410173d46e190bbd6c01e1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="debug-page-project-designer"></a>[デバッグ] ページ (プロジェクト デザイナー)
> [!WARNING]
>  このトピックは UWP アプリには適用されません。 Windows デベロッパー センターの「[デバッグ セッションの開始 (VB、C#、C++、および XAML)](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)」を参照してください。  
  
 Visual Basic または C# プロジェクトのデバッグ動作のプロパティを設定するには、**プロジェクト デザイナー**の **[デバッグ]** ページを使用します。  
  
 **[デバッグ]** ページにアクセスするには、**ソリューション エクスプローラー**でプロジェクト ノードを選択します。 **[プロジェクト]** メニューの *[プロジェクト名***プロパティ]** を選択します。 **プロジェクト デザイナー**が表示されたら、**[デバッグ]** タブをクリックします。  
  
## <a name="configuration-and-platform"></a>構成およびプラットフォーム  
 次のオプションを使用すると、表示または変更する構成およびプラットフォームを選択できます。  
  
 **構成**  
 表示または変更する構成設定を指定します。 設定は、**[デバッグ]** (既定)、**[リリース]**、または **[すべての構成]** のいずれかになります。 詳細については、「[デバッグ構成およびリリース プロジェクト構成](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e)」を参照してください。  
  
 **プラットフォーム**  
 表示または変更するプラットフォーム設定を指定します。 **[Any CPU]** (既定)、**[x64]**、および **[x86]** から選択できます。 詳細については、「[デバッグ構成およびリリース プロジェクト構成](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e)」を参照してください。  
  
## <a name="start-action"></a>開始動作  
 **[開始動作]** は、アプリケーションをデバッグするときに開始するアイテムを示します。プロジェクト、カスタム プログラム、URL のいずれかを指定できます。また、省略することもできます。 既定では、このオプションは **[プロジェクトの開始]** に設定されます。 **[デバッグ]** ページの **[開始動作]** 設定で、`StartAction` プロパティの値が決まります。  
  
 **プロジェクトの開始**  
 アプリケーションのデバッグ時に、実行可能ファイル (Windows アプリケーションとコンソール アプリケーション プロジェクトの場合) を起動することを指定するには、このオプションを選択します。 既定では、このオプションはオンです。  
  
 **外部プログラムの開始**  
 アプリケーションのデバッグ時に特定のプログラムが起動されるように指定するには、このオプションを選択します。  
  
 **ブラウザーを開始時に使用する URL**  
 アプリケーションのデバッグ時に特定の URL にアクセスすることを指定するには、このオプションを選択します。  
  
## <a name="start-options"></a>開始オプション  
 **コマンド ライン引数**  
 このテキスト ボックスには、デバッグに使用するコマンド ライン引数を入力します。  
  
 **作業ディレクトリ**  
 このテキスト ボックスには、プロジェクトの起動元のディレクトリを入力します。 または参照ボタン (**[...]**) をクリックしてディレクトリを選択します。  
  
 **リモート コンピューターの使用**  
 リモート コンピューターからアプリケーションをデバッグするには、このチェック ボックスをオンにし、テキスト ボックスにリモート コンピューターへのパスを入力します。  
  
## <a name="enable-debuggers"></a>デバッガーを有効にする  
 **アンマネージ コード デバッグを有効にする**  
 このオプションでは、ネイティブ コードのデバッグをサポートするかどうかを指定します。 COM オブジェクトを呼び出すか、プロジェクトを呼び出すネイティブ コードで記述されたカスタム プログラムを起動して、ネイティブ コードをデバッグする必要がある場合はこのチェック ボックスをオンにします。 アンマネージ コードのデバッグを無効にする場合は、このチェック ボックスをオフにします。 既定では、このチェック ボックスはオフです。  
  
 **SQL Server デバッグを有効にする**  
 Visual Basic アプリケーションから SQL プロシージャのデバッグを有効または無効にする場合は、このチェック ボックスをオンまたはオフにします。 既定では、このチェック ボックスはオフです。  
  
 **Visual Studio ホスティング プロセスを有効にする**  
 Visual Studio ホスティング プロセスを有効にする場合は、このチェック ボックスをオンにします。 既定では、このチェック ボックスはオンです。 詳細については、「[ホスト プロセス (vshost.exe)](../../ide/hosting-process-vshost-exe.md)」を参照してください。  
  
 セキュリティ ゾーンでデバッグするには、このオプションと、[[セキュリティの詳細設定] ダイアログ ボックス](../../ide/reference/advanced-security-settings-dialog-box.md)の **[選択されたアクセス許可セットでこのアプリケーションをデバッグする]** を有効にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデバッグ](../../debugger/debugging-in-visual-studio.md)   
 [C# デバッグ構成のプロジェクト設定](../../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic デバッグ構成のプロジェクト設定](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [デバッグ プロパティの管理](http://msdn.microsoft.com/en-us/92474d16-e7fe-4fac-9287-6bd6b3a7eb68)   
 [方法 : アクセス許可が制限された ClickOnce アプリケーションをデバッグする](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [方法 : 構成を作成および編集する](../../ide/how-to-create-and-edit-configurations.md)