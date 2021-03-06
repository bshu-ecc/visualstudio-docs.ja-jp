---
title: "IEnumDebugPortSuppliers2::Next |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPortSuppliers2::Next
helpviewer_keywords: IEnumDebugPortSuppliers2::Next
ms.assetid: e2a2d226-e70b-42c2-bf00-a936517940c8
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 139edb87a285b31d267fd16f77f1962a9966b950
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugportsuppliers2next"></a>IEnumDebugPortSuppliers2::Next
列挙体から次の要素のセットを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT Next(  
   ULONG                 celt,  
   IDebugPortSupplier2** rgelt,  
   ULONG*                pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint                  celt,  
   IDebugPortSupplier2[] rgelt,  
   ref uint              pceltFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]取得する要素の数。 また、最大のサイズを指定、`rgelt`配列。  
  
 `rgelt`  
 [入力、出力].配列[IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)格納する要素。  
  
 `pceltFetched`  
 [out]実際に返される要素の数を返します`rgelt`です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`です。 返します`S_FALSE`要求された要素数より少ないは返されませんでした。 それ以外の場合、エラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)