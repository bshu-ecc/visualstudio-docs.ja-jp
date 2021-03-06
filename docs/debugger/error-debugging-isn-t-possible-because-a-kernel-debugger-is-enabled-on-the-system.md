---
title: "エラー: デバッグではありません &#39; Possible Because a Kernel Debugger t が有効なシステムの |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.kernel_dbg_enabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: kernel debugger
ms.assetid: 630a7abd-3303-4aaa-888a-6de3de14bc01
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 448dbc486d58bc46e531b92de9f78272e4304d27
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="error-debugging-isn39t-possible-because-a-kernel-debugger-is-enabled-on-the-system"></a>エラー: デバッグではありません &#39; Possible Because a Kernel Debugger t が有効なシステムの
マネージ コードのデバッグ時に、次のエラー メッセージが表示されることがあります。  
  
```  
Debugging isn't possible because a kernel debugger is enabled on the system  
```  
  
 このメッセージは次の場合にマネージ コードをデバッグしようとすると表示されます。  
  
-   [!INCLUDE[win7](../debugger/includes/win7_md.md)] または [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] システムがデバッグ モードで起動している。  
  
-   アプリケーションが CLR バージョン CLR 2.0、3.0、または 3.5 を使用している。  
  
## <a name="solution"></a>ソリューション  
  
#### <a name="to-fix-this-problem"></a>この問題を解決するには  
  
-   CLR バージョン 4.0 または 4.5 を使用するようにアプリケーションをアップグレードします。  
  
     または  
  
-   カーネル デバッグを無効にし、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] でデバッグを実行します。  
  
     または  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] の代わりにカーネル デバッガーを使用してデバッグを実行します。  
  
     または  
  
-   カーネル デバッガーで、ユーザー モード例外を無効にします。  
  
#### <a name="to-disable-kernel-debugging-in-the-current-session"></a>現在のセッションでカーネル デバッグを無効にするには  
  
-   コマンド プロンプトで次のように入力します。  
  
    ```  
    Kdbgctrl.exe -d  
    ```  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-windows-vista-and-windows-7"></a>すべてのセッションでカーネル デバッグを無効にするには (Windows Vista および Windows 7)  
  
1.  コマンド プロンプトで次のように入力します。  
  
    ```  
    bcdedit /debug off   
    ```  
  
2.  コンピューターを再起動します。  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-other-windows-operating-systems"></a>すべてのセッションでカーネル デバッグを無効にするには (その他の Windows オペレーティング システム)  
  
1.  システム ドライブの boot.ini を探します (通常は c:\\)。 boot.ini ファイルは、読み取り専用で非表示になっていることがあります。 この場合、次のコマンドを使用して表示する必要があります。  
  
    ```  
    dir /ASH  
    ```  
  
2.  boot.ini をメモ帳で開き、次のオプションを削除します。  
  
    ```  
    /debug  
    /debugport  
    /baudrate  
    ```  
  
3.  コンピューターを再起動します。  
  
#### <a name="to-debug-with-the-kernel-debugger"></a>カーネル デバッガーを使用してデバッグを実行するには  
  
1.  カーネル デバッガーがフックされている場合、デバッグを続行するかどうかを確認するメッセージが表示されます。 ボタンをクリックして続行します。  
  
2.  `User break exception(Int 3).` が発生することがあります。その場合は、次のカーネル デバッガー コマンドを入力してデバッグを続行します。  
  
     `gn`  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [マネージ コードをデバッグする](../debugger/debugging-managed-code.md)