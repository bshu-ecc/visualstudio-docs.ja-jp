---
title: "Idiastackframe::get_rawlvarinstancevalue |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5559ad617afbb2ae4a65ecbf399f7f79d93ae1c7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
このメソッドは、実際のバイト数として指定されたローカル変数の値を取得します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pInstance`  
 [in]`IDiaLVarInstance`ローカル変数の値を取得するのインスタンスを表すオブジェクト。  
  
 `cbDataMax`  
 [in]バッファー内のバイトの最大数を指す`pbData`です。 これは、8 バイトの最大数を指定できます (`sizeof(ULONGLONG)`)。  
  
 `pcbData`  
 [out]実際のバッファーに格納されるバイト数を返します。  
  
 `pbData`  
 [out]データを使用して入力バッファーです。 これは、ことはできません`NULL`です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)