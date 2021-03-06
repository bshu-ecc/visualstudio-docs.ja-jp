---
title: "IDebugCoreServer3::GetServerFriendlyName |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3::GetServerFriendlyName
helpviewer_keywords: IDebugCoreServer3::GetServerFriendlyName
ms.assetid: 7035b904-b3d7-4d9b-98d9-65714b8a8b9f
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9ad20c8b71132b87efae6f2b4d27b7339e574cc4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcoreserver3getserverfriendlyname"></a>IDebugCoreServer3::GetServerFriendlyName
サーバーのフレンドリ名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetServerFriendlyName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetServerFriendlyName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrName`  
 [out]サーバーのフレンドリ名を返します。  
  
> [!NOTE]
>  呼び出し元は、文字列を解放します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 ユーザーが起動のサーバーでは、このメソッドによって返される名前は、サーバーの完全な名前です。 サーバーの自動起動の名前は、マシンのサーバーが実行されていることです。  
  
 コンピューター対象の名前では、呼び出し、 [GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)