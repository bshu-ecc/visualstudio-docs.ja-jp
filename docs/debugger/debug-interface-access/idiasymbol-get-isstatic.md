---
title: "IDiaSymbol::get_isStatic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSymbol::get_isStatic メソッド"
ms.assetid: 3be5fe1b-46e8-4b07-90d8-4929dbbe7ff7
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSymbol::get_isStatic
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

関数やサンクのレイヤーをとしてマークされているかどうかを指定するフラグを取得します。  
  
## 構文  
  
```cpp  
HRESULT get_isStatic(  
   BOOL *pFlag  
);  
```  
  
#### パラメーター  
 `pFlag`  
 \[入力\] 関数やサンクのレイヤーが静的としてマークされている場合はを返します `TRUE` ; それ以外の場合戻り `FALSE`。  
  
## 戻り値  
 正常に終了した場合戻り `S_OK`; それ以外の場合戻り `S_FALSE` またはエラー コード。  
  
> [!NOTE]
>  `S_FALSE` の戻り値はプロパティのシンボルで使用できないことを意味します。  
  
## 必要条件  
  
|必要条件|Description|  
|----------|-----------------|  
|ヘッダー:|dia2.h|  
|バージョン :|DIA SDK v8.0|  
  
## 参照  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)