---
title: "Log Command Window Output コマンド | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 21450a0478bb7f2388cdde6b69f6fe661e9a055c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="log-command-window-output-command"></a>LogCommandWindowOutput コマンド
**[コマンド]** ウィンドウの入出力をすべてファイルにコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]  
```  
  
## <a name="arguments"></a>引数  
 `filename`  
 省略可能です。 ログ ファイルの名前。 既定では、ユーザーのプロファイル フォルダーにファイルが作成されます。 ファイル名が既に存在する場合、ログは、既存のファイルの末尾に追加されます。 ファイルが指定されていない場合は、指定された最後のファイルが使用されます。 以前のファイルが存在しない場合、cmdline.log と呼ばれる既定のログ ファイルが作成されます。  
  
> [!TIP]
>  ログ ファイルの保存先を変更するには、ファイルの完全パスを入力します。パスに空白が含まれる場合は、パスを引用符で囲みます。  
  
## <a name="switches"></a>スイッチ  
 /on  
 省略可能です。 指定したファイルで **[コマンド]** ウィンドウのログの作成を開始し、ファイルに新しい情報を追加します。  
  
 /off  
 省略可能です。 **[コマンド]** ウィンドウのログの作成を停止します。  
  
 /overwrite  
 省略可能です。 `filename` 引数に指定したファイル名が既存のファイルと同じ場合は、既存のファイルが上書きされます。  
  
## <a name="remarks"></a>コメント  
 ファイルを指定しない場合、既定では、ファイル cmdline.log が作成されます。 既定では、このコマンドのエイリアスは Log です。  
  
## <a name="examples"></a>例  
 次の例では、新規のログ ファイル cmdlog を作成して、コマンドのログを開始します。  
  
```  
>Tools.LogCommandWindowOutput cmdlog  
```  
  
 次の例では、コマンドのログを停止します。  
  
```  
>Tools.LogCommandWindowOutput /off  
```  
  
 次の例では、以前のログ ファイルを使用してコマンドのログを再開します。  
  
```  
>Tools.LogCommandWindowOutput /on  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)   
 [コマンド ウィンドウ](../../ide/reference/command-window.md)   
 [[検索/コマンド] ボックス](../../ide/find-command-box.md)   
 [Visual Studio コマンドのエイリアス](../../ide/reference/visual-studio-command-aliases.md)