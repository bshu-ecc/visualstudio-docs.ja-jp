---
title: "Symbol Path コマンド | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d446779e4f84bf19e965393f9fa1142c7e4e166a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="symbol-path-command"></a>Symbol Path コマンド
デバッガーによってシンボルが検索されるディレクトリの一覧を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## <a name="arguments"></a>引数  
 `pathname`  
 省略可能です。 デバッガーによってシンボルが検索されるパスを、セミコロンで区切った一覧です。  
  
## <a name="remarks"></a>コメント  
 `pathname` を指定しない場合、シンボル用の現在のパスがコマンドによって一覧表示されます。  
  
## <a name="example"></a>例  
 次の例では、シンボル ディレクトリの一覧に 2 つのパスを追加します。  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## <a name="example"></a>例  
 次の例では、シンボル用の現在のパスをセミコロンで区切った一覧が表示されます。  
  
```  
Debug.SymbolPath  
```  
  
## <a name="see-also"></a>関連項目  
 [コマンド ウィンドウ](../../ide/reference/command-window.md)   
 [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)