---
title: "[メッセージ] タブ ([メッセージ オプション] ダイアログ ボックス) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "メッセージ オプション、メッセージ"
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# [メッセージ] タブ ([メッセージ オプション] ダイアログ ボックス)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

\[メッセージ\] タブを使用すると、[メッセージ ビュー](../debugger/messages-view.md)に一覧表示するメッセージの種類を選択したり、メッセージの検索条件を指定したりできます。  [&#91;メッセージ オプション&#93; ダイアログ ボックス](../debugger/message-options-dialog-box.md)を表示するには、\[スパイ\] メニューの \[メッセージのログ出力\] をクリックします。  
  
 通常は、まずメッセージ グループを選択します。その後で、表示するメッセージを個別に選択して、選択内容を細かく調整します。  \[すべて\] ボタンをクリックすると、すべてのメッセージの種類が選択されます。\[なし\] ボタンをクリックすると、すべての種類の選択が解除されます。  
  
 \[メッセージ\] タブには、次の項目があります。  
  
 **\[表示するメッセージ\]**  
 表示する個別のメッセージを選択します。  新たに作成したメッセージ ウィンドウには、すべてのメッセージを表示できます。  \[メッセージ\] タブでメッセージをフィルター処理する場合、そのフィルターは新しいメッセージにのみ適用されます。既にウィンドウ ビューに表示されているメッセージには適用されません。  
  
 **\[メッセージ グループ\]**  
 表示するメッセージのグループを選択します。  次のグループを選択できます。  
  
-   \[WM\_USER\]: コードが WM\_USER 以上のメッセージ。  
  
-   \[登録された\]: **RegisterWindowMessage** の呼び出しによって登録されたメッセージ。  
  
-   \[不明\]: 0 ～ "WM\_USER – 1" の範囲にある不明なメッセージ。  
  
 これらのメッセージ グループは、\[表示するメッセージ\] の特定のエントリには対応していません。  グループを選択したとき、選択内容はメッセージ ストリームに直接適用されます。  
  
 \[メッセージ グループ\] 内の淡色表示になっているチェック ボックスは、\[表示するメッセージ\] ボックスの一覧でそのグループ内のメッセージに関係する変更が行われていること、つまりそのグループ内のメッセージの種類の一部が選択されていないことを示しています。  
  
 **\[設定を既定値として保存\]**  
 後で使用できるように、現在の設定をメッセージの検索オプションとして保存します。  これらの設定も、現在の Spy\+\+ を終了したときに保存されます。