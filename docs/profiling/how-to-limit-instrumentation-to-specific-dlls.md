---
title: "方法: インストルメンテーションを特定の DLL に制限する | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: performance tools, runtime profiling control window
ms.assetid: 17c5996f-e3d0-4e44-b175-52b401b0f2d5
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 59d24a6cc67429fb6c0231f9487d80abe91de965
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-limit-instrumentation-to-specific-dlls"></a>方法 : インストルメンテーションを特定の DLL に制限する
インストルメンテーション プロファイリング方式を使用すると、プロファイリング データの収集をアプリケーションの 1 つ以上の DLL に制限することができます。 アプリケーションの 1 つ以上の DLL をプロファイルするには、ターゲットとして .dll ファイルを含むパフォーマンス セッションを作成します。 プロファイルする DLL は、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ソリューションのプロジェクトとしてまたは独立したバイナリ ファイルとして指定できます。  
  
### <a name="to-limit-instrumentation-to-specific-dlls-in-a-visual-studio-solution"></a>インストルメンテーションを Visual Studio ソリューションの特定の DLL に制限するには  
  
1.  [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] で DLL を含むソリューションを開きます。  
  
2.  **[分析]** メニューの **[パフォーマンス ウィザードの起動]** を選択します。  
  
3.  プロファイリング方式として **[インストルメンテーション]** を選択し、**[次へ]** をクリックします。  
  
4.  **[次の使用可能なターゲットからプロファイルするターゲットを選択]** で .dll プロジェクトの名前を選択し、**[次へ]** をクリックします。  
  
5.  **[完了]** をクリックしてウィザードを終了すると、**[パフォーマンス エクスプローラー]** ウィンドウに新しいパフォーマンス セッションが表示されます。  
  
6.  **[ターゲット]** を右クリックして **[ターゲット プロジェクトの追加]** を選択します。  
  
7.  **[ターゲット プロジェクトの追加]** リストで、DLL を実行するために使用する実行可能なプロジェクトを選択します。  
  
     省略可能です。 プロファイルする DLL プロジェクトはいくつでも追加できます。  
  
8.  追加されたプロジェクトのデータ収集を回避するには、プロジェクトの名前を右クリックし、**[インストルメント]** チェック ボックスをオフにします。  
  
### <a name="to-specify-specific-dlls-to-profile-as-independent-binaries"></a>プロファイルする特定の DLL を独立したバイナリとして指定するには  
  
1.  [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] を開きます。  
  
2.  **[分析]** メニューの **[パフォーマンス ウィザードの起動]** を選択します。  
  
3.  **[次の使用可能なターゲットからプロファイルするターゲットを選択]** で **[ダイナミック リンク ライブラリ (.DLL) のプロファイル]** を選択して、**[次へ]** をクリックします。  
  
4.  ウィザードの 2 ページ目で次の手順を実行します。  
  
    -   プロファイルする .dll ファイルのパスとファイル名を **[DLL パス]** に入力します。 省略記号ボタン (...) をクリックして、**[プロファイルするダイナミック リンク ライブラリ]** ダイアログ ボックスでファイルを指定することもできます。 次の手順で選択する実行可能 (.exe) ファイルによって起動される .dll ファイルのコピーを指定する必要があることにご注意ください。  
  
    -   .dll を実行する実行可能 (.exe) ファイルのパスとファイルの名前を **[実行可能ファイルのパス]** に入力します。 省略記号ボタン (...) をクリックして、**[起動する実行可能ファイル]** ダイアログ ボックスでファイルを指定することもできます。  
  
    -   省略可能です。 実行可能ファイルに渡すコマンド ライン引数があれば、**[コマンド ライン引数]** に入力します。 必要に応じて、アプリケーションの作業ディレクトリを **[作業ディレクトリ]** に指定します。  
  
    -   **[次へ]**をクリックします。  
  
5.  プロファイリング方式として **[インストルメンテーション]** を選択し、**[次へ]** をクリックします。  
  
6.  **[完了]** をクリックしてウィザードを終了すると、**[パフォーマンス エクスプローラー]** ウィンドウに新しいパフォーマンス セッションが表示されます。  
  
7.  省略可能です。 .dll ファイルをさらに追加するには、**[ターゲット]** を右クリックし、**[ターゲット バイナリの追加]** を選択します。 **[ターゲット バイナリの追加]** ダイアログ ボックスからファイルを選択します。  
  
    > [!NOTE]
    >  DLL を実行する実行可能 (.exe) ファイルは指定しないでください。  
  
## <a name="see-also"></a>関連項目  
 [データ収集の制御](../profiling/controlling-data-collection.md)   
 [方法: インストルメンテーションを特定の関数に制限する](../profiling/how-to-limit-instrumentation-to-specific-functions.md)