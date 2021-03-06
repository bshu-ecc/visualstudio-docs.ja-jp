---
title: "コマンド ラインからの階層相互作用データの追加 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tier interaction profiling method
- profiling tools,tier interaction method
ms.assetid: 5a35647f-03f2-4555-8eeb-fda7e0080e67
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a210ce1f6aeac113033bd82306bb5b682a5e21b9
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
# <a name="adding-tier-interaction-data-from-the-command-line"></a>コマンド ラインからの階層相互作用データの追加
階層相互作用プロファイリングにより、1 つ以上のデータベースと通信する多階層アプリケーションの関数で同期 [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] の呼び出しの実行時間に関する追加情報が提供されます。  
  
 **Windows 8 と Windows Server 2012**  
  
 Windows 8 デスクトップ アプリおよび Windows Server 2012 アプリで階層相互作用データを収集するには、インストルメンテーション メソッドを使用する必要があります。 UWP アプリで階層相互作用データの収集はサポートされていません。  
  
 **Visual Studio のエディション**  
  
 階層相互作用プロファイル データは、[!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)]、[!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]、または [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)] を使用して収集できます。 ただし、階層相互作用プロファイル データを表示できるのは、[!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] および [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] のみです。  
  
 **リモート コンピューターでの TIP データの収集**  
  
 リモート コンピューターで階層相互作用データを収集するには、Visual Studio コンピューターの *%VSInstallDir%***\Team Tools\Performance Tools\Setups** フォルダーから **vs_profiler_***\<Platform>***_***\<Language>***.exe** ファイルをリモート コンピューターにコピーしてインストールする必要があります。 [リモート デバッグ](../debugger/remote-debugging.md)のダウンロード パッケージにあるプロファイリング ツールを使用することはできません。  
  
 **TIP レポート**  
  
 階層相互作用データは、[!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] IDE でのみ表示できます。 [VSPerfReport](../profiling/vsperfreport.md) の使用による、ファイル ベースの階層相互作用レポートは利用できません。  
  
## <a name="adding-tier-interaction-data-with-vsperfcmd"></a>VSPerfCmd に階層相互作用データを追加する  
 VSPerfASPNETCmd コマンド ライン ツールを使用すると、プロファイリング ツールで使用できるすべての機能にアクセスできます。 VSPerfCmd を使用して収集されたプロファイリング データに階層相互作用を追加するには、**VSPerfCLREnv** ユーティリティを使用して階層相互作用データを有効にする環境変数を設定して削除する必要があります。 指定するオプションとデータを収集するために必要な手順は、プロファイリングするアプリケーションの種類によって異なります。  
  
### <a name="profiling-stand-alone-applications"></a>スタンドアロン アプリケーションのプロファイリング  
 別のプロセス (SQLServer に対して同期 [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] 呼び出しを行う Windows デスクトップ アプリケーションなど) によって実行されないアプリケーションに階層相互作用データを追加するには、**VSPerfClrEnv /InteractionOn** オプションを使用して環境変数を設定し、**VSPerfClrEnv /InteractionOff** オプションを使用してそれらを削除します。  
  
 次の例では、Windows デスクトップ アプリケーションはインストルメンテーション メソッドを使用してプロファイルされ、階層相互作用データが収集されます。  
  
##### <a name="profiling-a-windows-desktop-application-example"></a>Windows デスクトップ アプリケーションのプロファイルの例  
  
1.  管理者特権を使用して、コマンド プロンプト ウィンドウを開きます。 **[スタート]** ボタンをクリックし、**[すべてのプログラム]**、**[アクセサリ]** の順にポイントします。 **[コマンド プロンプト]** を右クリックしてから、**[管理者として実行]** をクリックします。  
  
2.  .NET プロファイル環境変数と TIP を環境変数初期化します。 次のコマンドを入力します。  
  
    ```  
    vsperfclrenv /traceon  
    vsperfclrenv /interactionon  
    ```  
  
3.  プロファイラーを起動します。 次のコマンドを入力します。  
  
    ```  
    vsperfcmd /start:trace /output:Desktop_tip.vsp   
    ```  
  
4.  VSPerfCmd でアプリケーションを起動します。 次のコマンドを入力します。  
  
    ```  
    vsperfcmd /launch:DesktopApp.exe  
    ```  
  
5.  プロファイリング データを収集するアプリケーションを実行し、通常の方法でアプリケーションを終了します。  
  
6.  TIP 環境変数を削除します。 次のコマンドを入力します。  
  
    ```  
    vsperfclrenv /off  
    ```  
  
 詳細については、「[スタンドアロン アプリケーションのコマンド ラインによるプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)」を参照してください。  
  
### <a name="profiling-services"></a>サービスのプロファイリング  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリケーションなどのサービスをプロファイルするには、**VSPerfClrEnv /GlobalInteractionOn** オプションを使用して環境変数を設定し、**VSPerfClrEnv/GlobalInteractionOff** オプションを使用してそれらを削除します。  
  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web アプリケーションなどのサービスをプロファイルする際には、多くの場合、プロファイリングを有効にするためにコンピューターの再起動が必要になります。  
  
 次の例では、Windows サービスはインストルメンテーション メソッドを使用してプロファイルされ、階層相互作用データが収集されます。  
  
##### <a name="profiling-a-windows-service-example"></a>Windows サービスのプロファイリングの例  
  
1.  インストールの必要なサービスがあればインストールします。  
  
2.  管理者特権を使用して、コマンド プロンプト ウィンドウを開きます。 **[スタート]** ボタンをクリックし、**[すべてのプログラム]**、**[アクセサリ]** の順にポイントします。 **[コマンド プロンプト]** を右クリックしてから、**[管理者として実行]** をクリックします。  
  
3.  .NET プロファイル環境変数を初期化します。 次のコマンドを入力します。  
  
    ```  
    vsperfclrenv /globaltraceon  
    ```  
  
4.  TIP 環境変数を初期化します。 次のコマンドを入力します。  
  
    ```  
    vsperfclrenv /globalinteractionon  
    ```  
  
5.  コンピューターを再起動して環境変数を登録します。  
  
6.  管理者特権を使用して、コマンド プロンプト ウィンドウを開きます。  
  
7.  プロファイラーを起動します。 次のコマンドを入力します。  
  
    ```  
    vsperfcmd /start:trace /output:MiddleTier_tip.vsp /user:SYSTEM /crosssession   
    ```  
  
8.  起動の必要なサービスがあれば起動します。  
  
9. プロファイラーをサービスにアタッチします。 次のコマンドを入力します。  
  
    ```  
    vsperfcmd /attach:MiddleTier.exe /output:MyService_tip.vsp /user:SYSTEM /crosssession   
    ```  
  
10. サービスを実行し、プロファイル データを収集します。  
  
11. プロファイラーを停止します。 次のコマンドを入力します。  
  
     `vsperfcmd /detach`  
  
12. .NET および TIP プロファイル環境変数を削除します。 次のコマンドを入力します。  
  
    ```  
    vsperfclrenv /globaloff  
    ```  
  
13. コンピューターを再起動して、削除された環境変数を登録します。  
  
 詳細については、次のトピックを参照してください。  
  
 [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)  
  
 [プロファイリング (サービスの)](../profiling/command-line-profiling-of-services.md)  
  
## <a name="adding-tier-interaction-data-with-vsperfaspnetcmd"></a>VSPerfASPNETCmd に階層相互作用データを追加する  
 VSPerfASPNETCmd コマンド ライン ツールを使用すると、[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web アプリケーションを簡単にプロファイルできます。 **VSPerfCmd** コマンド ライン ツールと比較すると、オプションが減り、環境変数を設定する必要がなく、コンピューターを再起動する必要がありません。 VSPerfASPNETCmd のこれらの機能により、階層相互作用データの収集が非常に簡単になります。  
  
 VSPerfASPNETCmd を使用して収集されたデータのプロファイリングに階層相互作用を追加するには、**/TIP** オプションをコマンド ラインに追加します。 たとえば、インストルメンテーション メソッドを使用して [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web アプリケーション用に階層相互作用データを収集するには、次のコマンド ラインを使用します。  
  
```  
vsperfaspnetcmd /tip /trace http://localhost/MyWebApp  
```  
  
 VSPerfASPNETCmd の詳細については、「[VSPerfASPNETCmd を使用した迅速な Web サイト プロファイリング](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)」を参照してください。