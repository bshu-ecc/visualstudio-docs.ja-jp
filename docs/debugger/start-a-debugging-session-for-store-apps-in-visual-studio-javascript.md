---
title: "Visual Studio (JavaScript) での UWP アプリのデバッグ セッションを開始 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: fb91203f-2cf4-44d3-8ed9-93bc5aaa50b8
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 192000815a5d35056c88cf81de9956614c092284
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
# <a name="start-a-debugging-session-for-uwp-apps-in-visual-studio-javascript"></a>Visual Studio (JavaScript) での UWP アプリのデバッグ セッションを開始します。
![Windows と Windows Phone に適用](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 このトピックでは、JavaScript と HTML5 で記述された UWP アプリのデバッグ セッションを開始する方法について説明します。 1 回のキー入力でデバッグを開始できます。または、特定のシナリオのデバッグ セッションを構成してから、アプリの起動方法を選択できます。  
  
> [!NOTE]
>  XAML および Visual c#、Visual C、または Visual Basic で記述されたアプリでは、次を参照してください[(VB、c#、C++ および XAML) は、デバッグ セッションを開始。](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_In_this_topic"></a> このトピックの内容  
 [このトピックの内容](#BKMK_In_this_topic)  
  
 [デバッグを開始する簡単な方法](#BKMK_The_easy_way_to_start_debugging)  
  
 [デバッグ セッションを構成する](#BKMK_Configure_the_debugging_session)  
  
-   [プロジェクトのデバッグ プロパティ ページを開く](#BKMK_Open_the_debugging_property_page_for_the_project)  
  
-   [ビルド構成オプションを選択する](#BKMK_Choose_the_build_configuration_options)  
  
-   [配置ターゲットを選択する](#BKMK_Choose_the_deployment_target)  
  
-   [使用するデバッガーを選択する](#BKMK_Choose_the_debugger_to_use)  
  
-   [(省略可能)デバッグ セッションでアプリの起動を遅らせる](#BKMK__Optional__Delay_starting_app_in_the_debug_session)  
  
-   [(省略可能) ネットワーク ループバックを無効にする](#BKMK__Optional__Disable_network_loopbacks)  
  
 [デバッグ セッションを開始する](#BKMK_Start_the_debugging_session)  
  
-   [デバッグを開始する (F5)](#BKMK_Start_debugging__F5_)  
  
-   [デバッグは開始する (F5 キー) がアプリの起動は遅らせる](#BKMK_Start_debugging__F5__but_delay_the_app_start)  
  
 [デバッガーでインストール済みのアプリを起動する](#BKMK_Start_an_installed_app_in_the_debugger)  
  
 [実行中のアプリにデバッガーをアタッチする](#BKMK_Attach_the_debugger_to_a_running_app_)  
  
-   [デバッグ モードで実行するようにアプリを設定する](#BKMK_Set_the_app_to_run_in_debug_mode)  
  
-   [デバッガーをアタッチします。](#BKMK_Attach_the_debugger)  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a> デバッグを開始する簡単な方法  
 ![Windows にのみ適用されます](../debugger/media/windows_only_content.png "windows_only_content")  
  
1.  Visual Studio でアプリ ソリューションを開きます。  
  
2.  ソリューションに複数のプロジェクトが含まれている場合は、デバッグするプロジェクトがスタートアップ プロジェクトにあることを確認します。 ソリューション エクスプ ローラーでは、プロジェクトを選択し、**スタートアップ プロジェクトとして設定**コンテキスト メニュー。  
  
3.  F5 キーを押します。  
  
 ![Windows Phone にのみ適用されます](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Visual Studio によってアプリがビルドされ、アタッチされたデバッガーが起動します。 実行は、ブレークポイントに達するか、実行が手動で中断されるか、ハンドルされない例外が発生するか、アプリが終了するまで続行されます。 詳細については、次を参照してください。[クイック スタート: HTML のデバッグと CSS](../debugger/quickstart-debug-html-and-css.md)です。  
  
##  <a name="BKMK_Configure_the_debugging_session"></a> デバッグ セッションを構成する  
 スクリプトがコンパイルされていないため、ビルド構成とプラットフォーム設定は適用されません。 C++ またはマネージ コンポーネントをデバッグする場合は、設定、**構成**に**デバッグ**からターゲット プラットフォームを選択し、**構成**ダイアログ。  
  
###  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a> プロジェクトのデバッグ プロパティ ページを開く  
  
1.  ソリューション エクスプローラーでプロジェクトを選択します。 ショートカット メニューの **[プロパティ]**をクリックします。  
  
2.  展開して、**構成プロパティ**ノードを選択し**デバッグ**です。  
  
###  <a name="BKMK_Choose_the_build_configuration_options"></a> ビルド構成オプションを選択する  
  
1.  **[構成]** ボックスの一覧の **[デバッグ]** または **[(アクティブ) デバッグ]**をクリックします。  
  
2.  **[プラットフォーム]** ボックスの一覧で、ビルドするターゲット プラットフォームを選択します。 ほとんどの場合、 **Any CPU**をお勧めします。  
  
###  <a name="BKMK_Choose_the_deployment_target"></a> 配置ターゲットを選択する  
 Visual Studio コンピューター、ローカル コンピューター上の Visual Studio シミュレーター、またはリモート コンピューター上にアプリを配置してデバッグできます。 ターゲットを選択する、**起動するデバッガー**ボックスの一覧、**デバッグ**プロジェクトのプロパティ ページ。  
  
 ![Windows にのみ適用されます](../debugger/media/windows_only_content.png "windows_only_content")  
  
 UWP アプリからこれらのオプションのいずれかを選択、**ターゲット デバイス**一覧。  
  
|||  
|-|-|  
|**ローカル コンピューター**|ローカル コンピューターの現在のセッションでアプリをデバッグします。 参照してください[、ローカル コンピューター上の実行の UWP アプリ](../debugger/run-windows-store-apps-on-the-local-machine.md)です。|  
|**シミュレーター**|[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] アプリ用の Visual Studio シミュレーターでアプリをデバッグします。 シミュレーターは、ローカル コンピューターでは使用できないデバイスの機能 (タッチ ジェスチャやデバイスの回転など) をデバッグできるようにするデスクトップ ウィンドウです。 参照してください[シミュレーターでアプリの実行の UWP](../debugger/run-windows-store-apps-in-the-simulator.md)です。|  
|**リモート コンピューター**|ローカル コンピューターにイントラネットを介して接続されているかイーサネット ケーブルを使用して直接接続されているデバイス上のアプリをデバッグします。 リモートでデバッグするには、リモート デバイス上に Visual Studio リモート ツールがインストールされ、実行されている必要があります。 参照してください[をリモート コンピューターでの実行の UWP アプリ](../debugger/run-windows-store-apps-on-a-remote-machine.md)です。|  
  
 **[リモート コンピューター]**をクリックした場合は、次のいずれかの方法でリモート コンピューターの IP アドレスを指定します。  
  
-   名前またはにリモート コンピューターの IP アドレスを入力、**マシン名**ボックス。  
  
-   下向きの矢印を選択して、**マシン名**ボックスし、選択**\<検索 ...> >**です。 リモート コンピューターを選択**リモート デバッガー接続の選択** ダイアログ ボックス。  
  
     ![リモート デバッガー接続の選択](../debugger/media/vsrun_pro_selectremotedebuggerdlg.png "VSRUN_PRO_SelectRemoteDebuggerDlg")  
  
    > [!NOTE]
    >  [リモート デバッガー接続の選択] ダイアログ ボックスには、ローカル サブネット上にあるコンピューターとイーサネット ケーブルによって Visual Studio コンピューターに直接接続されているコンピューターが表示されます。 別のコンピューターを指定するには、 **[コンピューター名]** ボックスに名前を入力します。  
  
 ![Windows Phone にのみ適用されます](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Windows Phone アプリで次のように選択します。**デバイス**からエミュレーターの 1 つ、または、**ターゲット デバイス**リスト。  
  
###  <a name="BKMK_Choose_the_debugger_to_use"></a> 使用するデバッガーを選択する  
 既定では、デバッガーはアプリの JavaScript コードにアタッチします。 JavaScript コードの代わりに、アプリのコンポーネントのネイティブ C++ とマネージ コードをデバッグすることを選択できます。 デバッグするコードは、アプリ プロジェクトの **[デバッグ]** プロパティ ページの **[デバッガーの種類]** の一覧で指定します。  
  
 次のデバッガーのいずれかを選択、**デバッガーの種類**一覧。  
  
|||  
|-|-|  
|**スクリプトのみ**|アプリの JavaScript コードをデバッグします。 マネージ コードとネイティブ コードは無視されます。|  
|**ネイティブのみ**|アプリのネイティブ コードと C/C++ コードをデバッグします。 マネージ コードと JavaScript コードは無視されます。|  
|**スクリプトを含むネイティブ**|アプリのネイティブ C++ コードと JaveScript コードをデバッグします。|  
|**マネージのみ**|アプリのマネージ コードをデバッグします。 JavaScript コードとネイティブ C/C++ コードは無視されます。|  
|**混合 (マネージとネイティブ)**|アプリのネイティブ C/C++ コードとマネージ コードをデバッグします。 JavaScript コードは無視されます。|  
  
###  <a name="BKMK__Optional__Delay_starting_app_in_the_debug_session"></a>(省略可能)デバッグ セッションでアプリの起動を遅らせる  
 既定では、Visual Studio はデバッグの開始と同時にアプリを起動します。 デバッグ セッションは開始するが、アプリの起動は遅らせることもできます。 アプリは、[スタート] メニューから起動されたとき、アクティブ化コントラクトによって起動されたとき、または別のプロセスやメソッドによって起動されたときに、デバッガー内で起動します。 アプリの起動を遅らせることにより、アプリが実行されていないときに発生させるバックグラウンド イベントをアプリ内でデバッグすることもできます。  
  
 アプリの起動を遅らせるかどうかを指定する、**アプリケーションの起動**ボックスの一覧、**デバッグ**アプリ プロジェクトのプロパティ ページ。 次のオプションのいずれかを選択します。  
  
-   選択**いいえ**アプリの起動を遅らせるにします。  
  
-   選択**はい**をすぐにアプリを起動します。  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a> (省略可能) ネットワーク ループバックを無効にする  
 ![Windows にのみ適用されます](../debugger/media/windows_only_content.png "windows_only_content")  
  
 セキュリティ上の理由から、標準的な方法でインストールされている UWP アプリにインストールされているデバイスに対してネットワーク呼び出しを行うには許可されていません。 既定では、Visual Studio による配置では、配置されたアプリに対するこの規則の適用は免除されます。 この免除によって、1 台のコンピューター上で通信プロシージャをテストできます。 Microsoft ストアにアプリを送信する前に、この免除なしアプリをテストする必要があります。  
  
 ネットワーク ループバックの免除を削除する選択**いいえ**から、 **ネットワーク ループバックの許可**ボックスの一覧、**デバッグ**プロパティ ページ。  
  
##  <a name="BKMK_Start_the_debugging_session"></a> デバッグ セッションを開始する  
  
###  <a name="BKMK_Start_debugging__F5_"></a> デバッグを開始する (F5)  
 選択すると**デバッグの開始**上、**デバッグ**メニュー (キーボード: f5 キーを押して)、Visual Studio は、アタッチされたデバッガーでアプリケーションを起動します。 実行は、ブレークポイントに達するか、実行が手動で中断されるか、ハンドルされない例外が発生するか、アプリが終了するまで続行されます。  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a> デバッグは開始する (F5 キー) がアプリの起動は遅らせる  
 デバッグ モードで実行されるようにアプリを設定し、デバッガー以外の方法でアプリを起動できます。 たとえば、[スタート] メニューからのアプリの起動をデバッグしたり、アプリを起動せずにアプリのバックグラウンド プロセスをデバッグしたりできます。アプリの起動を遅らせるには、次の手順を実行します。  
  
1.  **デバッグ**アプリのページのプロジェクト プロパティで、選択**いいえ**から、**アプリケーションの起動**リスト。  
  
2.  選択**デバッグの開始**上、**デバッグ**メニュー (キーボード: f5 キーを押します)。  
  
3.  [スタート] メニュー、実行コントラクト、または別のプロシージャからアプリを起動します。  
  
 アプリがデバッグ モードで起動します。 実行は、ブレークポイントに達するか、実行が手動で中断されるか、ハンドルされない例外が発生するか、アプリが終了するまで続行されます。  
  
 。 バック グラウンド タスクのデバッグの詳細については、次を参照してください。[トリガー中断、再開、およびバック グラウンド イベント UWP アプリの)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)です。  
  
##  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a> デバッガーでインストール済みのアプリを起動する  
 F5 キーを使用してデバッグを開始すると、Visual Studio はアプリをビルドして配置し、デバッグ モードで実行されるようにアプリを設定してから起動します。 デバイスに既にインストールされているアプリを起動するには、[インストールされているアプリケーション パッケージのデバッグ] ダイアログ ボックスを使用します。 この方法は、Windows ストアからインストールされたアプリをデバッグする必要がある場合や、アプリのソース ファイルはあってもアプリの Visual Studio プロジェクトがない場合に役立ちます。 Visual Studio プロジェクトやソリューションを使用しないカスタム ビルド システムがこれに該当します。  
  
 アプリはローカル デバイスにインストールすることも、リモート デバイスにインストールすることもできます。  アプリをすぐに起動できます。また、アプリを別のプロセスや方法で起動したときに ([スタート] メニューからの起動や、アクティブ化コントラクトによる起動など)、デバッガーで実行するようにアプリを設定することもできます。アプリを起動せずにバックグラウンド プロセスをデバッグする場合は、デバッグ モードで実行されるようにアプリを設定できます。 詳細については、次を参照してください。[トリガー中断、再開、およびバック グラウンド イベント UWP アプリの)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)です。  
  
 インストール済みのアプリがデバッグ モードで実行されるように設定するには、次の手順を実行します。  
  
> [!NOTE]
>  この手順は、アプリが実行されていないときに開始してください。  
  
1.  **デバッグ**] メニューの [選択**インストール済みアプリ パッケージのデバッグ**です。  
  
2.  一覧から次のいずれかのオプションを選択します。  
  
    |||  
    |-|-|  
    |**ローカル コンピューター**|ローカル コンピューターの現在のセッションでアプリをデバッグします。 参照してください[、ローカル コンピューター上の実行の UWP アプリ](../debugger/run-windows-store-apps-on-the-local-machine.md)です。|  
    |**シミュレーター**|[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] アプリ用の Visual Studio シミュレーターでアプリをデバッグします。 シミュレーターは、ローカル コンピューターでは使用できないデバイスの機能 (タッチ ジェスチャやデバイスの回転など) をデバッグできるようにするデスクトップ ウィンドウです。 参照してください[シミュレーターでアプリの実行の UWP](../debugger/run-windows-store-apps-in-the-simulator.md)です。|  
    |**リモート コンピューター**|ローカル コンピューターにイントラネットを介して接続されているかイーサネット ケーブルを使用して直接接続されているデバイス上のアプリをデバッグします。 リモートでデバッグするには、リモート デバイス上に Visual Studio リモート ツールがインストールされ、実行されている必要があります。 参照してください[をリモート コンピューターでの実行の UWP アプリ](../debugger/run-windows-store-apps-on-a-remote-machine.md)です。|  
  
3.  **[インストールされているアプリケーション パッケージ]** ボックスの一覧からアプリを選択します。  
  
4.  **[このコードの種類をデバッグ]** ボックスの一覧から、使用するデバッグ エンジンを選択します。  
  
5.  (省略可能) 他の方法で起動したアプリをデバッグするときや、バックグラウンド プロセスをデバッグするときは、 **[起動しないが、開始時にコードをデバッグ]** を選択します。  
  
 **[開始]**をクリックすると、アプリが起動するか、デバッグ モードで実行するように設定されます。  
  
##  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> 実行中のアプリにデバッガーをアタッチする  
 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] アプリにデバッガーをアタッチするには、デバッグ可能パッケージ マネージャーを使用して、デバッグ モードで実行するようにアプリを設定する必要があります。 デバッグ可能パッケージ マネージャーは、Visual Studio リモート ツールと共にインストールされます。  
  
 アプリへのデバッガーのアタッチは、インストール済みのアプリ (Windows ストアからインストールされたアプリなど) をデバッグする場合に役立ちます。 アタッチは、アプリのソース ファイルはあるが、アプリの Visual Studio プロジェクトがない場合に必要です。 Visual Studio プロジェクトやソリューションを使用しないカスタム ビルド システムがこれに該当します。  
  
 アプリをアタッチするには  
  
1.  デバッグ モードで実行するようにアプリを設定します。 これは、アプリが実行されていないときに行う必要があります。  
  
2.  アプリを起動します。 アプリの起動は、[スタート] メニュー、実行コントラクト、または他の方法で実行できます。  
  
3.  実行中のアプリにデバッガーをアタッチします。  
  
###  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> デバッグ モードで実行するようにアプリを設定する  
  
1.  アプリをインストールするデバイスに Visual Studio リモート ツールをインストールします。 参照してください[remote tools のインストール](http://msdn.microsoft.com/library/windows/apps/hh441469.aspx#BKMK_Installing_the_Remote_Tools)です。  
  
2.  [スタート] メニューで`Debuggable Package Manager`を検索して起動します。  
  
     AppxDebug コマンドレット用に適切に構成された PowerShell ウィンドウが表示されます。  
  
3.  アプリのデバッグを有効にするには、アプリの PackageFullName 識別子を指定する必要があります。 PackageFullName を含むすべてのアプリの一覧を表示するには、PowerShell プロンプトに「 `Get-AppxPackage` 」と入力します。  
  
4.  PowerShell プロンプトに「 `Enable-AppxDebug` *PackageFullName* 」と入力します。 *PackageFullName* はアプリの PackageFullName 識別子です。  
  
###  <a name="BKMK_Attach_the_debugger"></a> デバッガーをアタッチします。  
  
> [!TIP]
>  JavaScript アプリは、wwahost.exe プロセスのインスタンスで実行されます。 アプリにアタッチする際に他の JavaScript アプリが実行されている場合、そのアプリが実行されている wwahost.exe の数値型プロセス ID (PID) を確認する必要があります。  
>   
>  このような状況に対処する最も簡単な方法は、他の JavaScript アプリをすべて閉じることです。 別の方法として、アプリを起動する前に Windows タスク マネージャーを開き、wwahost.exe プロセスの ID を確認できます。 アタッチするプロセスを指定すると、**選択可能なプロセス**ダイアログ ボックスで、アプリの wwahost.exe が、id をメモしたものとは異なります。  
  
 デバッガーをアタッチするには:  
  
1.  **[デバッグ]** メニューの **[プロセスにアタッチ]**をクリックします  
  
     **[プロセスにアタッチ]** ダイアログ ボックスが表示されます。  
  
2.  リモート デバイス上のアプリにアタッチするには、 **[修飾子]** ボックスにリモート デバイスを指定します。 次の操作を行うことができます。  
  
    -   **[修飾子]** ボックスに名前を入力します。  
  
    -   下向きの矢印を選択して、**修飾子**ボックスし、前にアタッチしたデバイスの一覧からデバイスを選択します。  
  
    -   選択**検索**ローカル サブネット上のデバイスの一覧からデバイスを選択します。  
  
3.  デバッグするコードの種類を **[アタッチ先]** ボックスに指定します。  
  
     **[選択]** をクリックし、次のいずれかを実行します。  
  
    -   選択**をデバッグするコードの種類を自動的に決定**です。  
  
    -   **[次のコードの種類をデバッグする]** をクリックし、一覧から 1 つ以上の型を選択します。  
  
4.  **選択可能なプロセス**一覧で、適切な選択**wwahost.exe**プロセスです。 使用して、**タイトル**アプリを識別する列。  
  
5.  **[アタッチ]**をクリックします。  
  
 Visual Studio によって、デバッガーがプロセスにアタッチされます。 実行は、ブレークポイントに達するか、実行が手動で中断されるか、ハンドルされない例外が発生するか、アプリが終了するまで続行されます。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ セッション (JavaScript) での実行制御](../debugger/control-execution-of-a-store-app-in-a-visual-studio-debug-session-for-windows-store-apps-javascript.md)   
 [クイック スタート: HTML および CSS をデバッグします。](../debugger/quickstart-debug-html-and-css.md)   
 [トリガーを中断、再開、およびバック グラウンド イベント UWP アプリの)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)   
 [Visual Studio でアプリをデバッグします。](../debugger/debug-store-apps-in-visual-studio.md)