---
title: "IEnumCodePaths2::Skip |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumCodePaths2::Skip
helpviewer_keywords: IEnumCodePaths2::Skip
ms.assetid: 356472d8-68b2-4b7e-b5f0-1f16d4ee80af
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e2dc00ec727be054ff05b08a968bdb52f8b33ee2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ienumcodepaths2skip"></a>IEnumCodePaths2::Skip
指定した要素数をスキップします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]スキップする要素の数。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`です。 返します`S_FALSE`場合`celt`残りの要素の数よりも大きいです。 それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 場合`celt`数より大きい値を指定して残りの要素の列挙体が最後に設定し、`S_FALSE`が返されます。  
  
## <a name="see-also"></a>関連項目  
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)