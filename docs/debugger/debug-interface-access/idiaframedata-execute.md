---
title: "Idiaframedata::execute |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29b284e466ce751e86f488203b4b22c0c18c6573
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
スタック アンワインドを実行し、スタック ウォーク フレーム インターフェイスで結果を返します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT execute (   
   IDiaStackWalkFrame* frame  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `frame`  
 [in][IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)フレーム レジスタの状態を保持するオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。 次の表は、このメソッドの戻り値を示します。  
  
|値|説明|  
|-----------|-----------------|  
|E_DIA_INPROLOG|プロローグ コードの中にスタック フレームを実行できません。|  
|E_DIA_SYNTAX|フレームのプログラムで発生したエラーを解析します。|  
|E_DIA_FRAME_ACCESS|アクセスのレジスタまたはメモリにできません。|  
|E_DIA_VALUE|値 (たとえば、0 による除算) の計算のエラーです。|  
  
## <a name="remarks"></a>コメント  
 このメソッドは、スタックをアンワインドするデバッグ中に呼び出されます。 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)オブジェクトは、レジスタに更新プログラムを受信しで使用されるメソッドを提供するクライアント アプリケーションによって実装される、`execute`メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)