---
title: "IEnumDebugFields |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFields
helpviewer_keywords: IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed697205a5cd7d866df639e2908e3cc0b4fa2f72
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
このインターフェイスを実装するオブジェクトのコレクションを表します、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```  
IEnumDebugFields : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 このインターフェイスは、シンボル プロバイダーを実装するオブジェクトのセットを指定する、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスです。 存在するための標準の COM 列挙ではないことに注意してください、 [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)メソッドです。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 このインターフェイスは、によって返される[GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)と[GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)です。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[次へ](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|次のセットを取得[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)列挙体からのオブジェクト。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|指定されたエントリ数をスキップします。|  
|[リセット](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|最初のエントリを列挙型をリセットします。|  
|[複製](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|現在の列挙型のコピーを取得します。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|列挙体のエントリの数を取得します。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="requirements"></a>要件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [シンボル プロバイダー インターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)   
 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)