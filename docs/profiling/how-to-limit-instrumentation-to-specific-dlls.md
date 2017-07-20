---
title: "方法 : インストルメンテーションを特定の DLL に制限する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "パフォーマンス ツール、[ランタイム プロファイル コントロール] ウィンドウ"
ms.assetid: 17c5996f-e3d0-4e44-b175-52b401b0f2d5
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# 方法 : インストルメンテーションを特定の DLL に制限する
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

インストルメンテーション プロファイリング方式を使用すると、プロファイリング データの収集をアプリケーションの 1 つ以上の DLL に制限することができます。  アプリケーションの 1 つ以上の DLL をプロファイルするには、ターゲットとして .dll ファイルを含むパフォーマンス セッションを作成します。  プロファイルする DLL は、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ソリューションのプロジェクトとしてまたは独立したバイナリ ファイルとして指定できます。  
  
### インストルメンテーションを Visual Studio ソリューションの特定の DLL に制限するには  
  
1.  [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] で DLL を含むソリューションを開きます。  
  
2.  **\[分析\]** メニューの **\[パフォーマンス ウィザードの起動\]** をクリックします。  
  
3.  プロファイリング方式として **\[インストルメンテーション\]** を選択し、**\[次へ\]** をクリックします。  
  
4.  **\[次の使用可能なターゲットからプロファイルするターゲットを選択\]** で、.dll プロジェクトの名前をクリックし、**\[次へ\]** をクリックします。  
  
5.  **\[完了\]** をクリックしてウィザードを終了すると、**\[パフォーマンス エクスプローラー\]** ウィンドウに新しいパフォーマンス セッションが表示されます。  
  
6.  **\[ターゲット\]** を右クリックし、**\[ターゲット プロジェクトの追加\]** をクリックします。  
  
7.  **\[ターゲット プロジェクトの追加\]** リストで、DLL を実行するために使用する実行可能なプロジェクトを選択します。  
  
     省略可能。  プロファイルする DLL プロジェクトはいくつでも追加できます。  
  
8.  追加されたプロジェクトのデータ収集を回避するには、プロジェクトの名前を右クリックし、**\[インストルメント\]** チェック ボックスをオフにします。  
  
### プロファイルする特定の DLL を独立したバイナリとして指定するには  
  
1.  [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] を開きます。  
  
2.  **\[分析\]** メニューの **\[パフォーマンス ウィザードの起動\]** をクリックします。  
  
3.  **\[次の使用可能なターゲットからプロファイルするターゲットを選択\]** で、**\[ダイナミック リンク ライブラリ \(.DLL\) のプロファイル\]** を選択し、**\[次へ\]** をクリックします。  
  
4.  ウィザードの 2 番目のページで、次の手順を実行します。  
  
    -   **\[Dll パス\]** に、プロファイルする .dll ファイルのパスとファイル名を入力します。  省略記号ボタン \(...\) をクリックして **\[プロファイルするダイナミック リンク ライブラリ\]** ダイアログ ボックスからファイルを検索することもできます。  次に選択する実行可能 \(.exe\) ファイルによって起動される .dll ファイルのコピーを指定する必要があります。  
  
    -   **\[実行可能パス\]** に、.dll を実行する実行可能 \(.exe\) ファイルのパスとファイル名を入力します。  省略記号ボタン \(...\) をクリックし、**\[起動する実行可能ファイル\]** ダイアログ ボックスからファイルを検索することもできます。  
  
    -   省略可能。  実行可能ファイルに渡すコマンド ライン引数があれば、**\[コマンド ライン引数\]** に入力します。  必要に応じて、**\[作業ディレクトリ\]** にアプリケーションの作業ディレクトリを指定します。  
  
    -   **\[次へ\]** をクリックします。  
  
5.  プロファイリング方式として **\[インストルメンテーション\]** を選択し、**\[次へ\]** をクリックします。  
  
6.  **\[完了\]** をクリックしてウィザードを終了すると、**\[パフォーマンス エクスプローラー\]** ウィンドウに新しいパフォーマンス セッションが表示されます。  
  
7.  省略可能。  .dll ファイルをさらに追加するには、**\[ターゲット\]** を右クリックし、**\[ターゲット バイナリの追加\]** をクリックします。  **\[ターゲット バイナリの追加\]** ダイアログ ボックスからファイルを選択します。  
  
    > [!NOTE]
    >  DLL を実行する実行可能 \(.exe\) ファイルは指定しないでください。  
  
## 参照  
 [データ収集の制御](../profiling/controlling-data-collection.md)   
 [方法 : インストルメンテーションを特定の関数に制限する](../profiling/how-to-limit-instrumentation-to-specific-functions.md)