---
title: "IDebugCoreServer2::GetMachineUtilities_V7 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords: IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 301af8eb2e6b317a532fec6dfdd5ac64f62d12a9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
このメソッドは、サーバーのマシン ユーティリティを取得します。  
  
> [!NOTE]
>  このメソッドは今後使用しません。 使用しないでください ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]は常に返します`E_NOTIMPL`このメソッドが呼び出された場合)。 歴史的な経緯によりは保持されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetMachineUtilities_V7(  
   IDebugMDMUtil2_V7** ppUtil  
);  
```  
  
```csharp  
int GetMachineUtilities_V7(  
   out IDebugMDMUtil2_V7 ppUtil  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppUtil`  
 [out]返します、`IDebugMDMUtil2_V7`マシン ユーティリティの情報を表すインターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 常に返します`E_NOTIMPL`を示すメソッドが実装されていません。  
  
## <a name="remarks"></a>コメント  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]常に返します`E_NOTIMPL`場合、このメソッドが呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)