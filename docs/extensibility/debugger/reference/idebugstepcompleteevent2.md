---
title: "IDebugStepCompleteEvent2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStepCompleteEvent2
helpviewer_keywords: IDebugStepCompleteEvent2 interface
ms.assetid: eba2b76e-f90d-486b-ae5c-c47f1b8ba2e5
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b0b96a1156d736332bdc8110ae2244fdfc9aad1b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idebugstepcompleteevent2"></a>IDebugStepCompleteEvent2
このインターフェイスは、デバッグ中のプログラムでは、ステップ イン、ステップ オーバー、またはソース コードまたはステートメントまたは命令の行外の手順が完了すると、セッション デバッグ マネージャー (SDM) に、デバッグ エンジン (DE) によって送信されます。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugStepCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デでは、ステップの操作の完了を報告するには、このインターフェイスを実装します。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)このインターフェイスと同じオブジェクトのインターフェイスを実装する必要があります。 SDM を使用して[QueryInterface](/cpp/atl/queryinterface)にアクセスする、`IDebugEvent2`インターフェイスです。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 デを作成し、ステップの操作の完了を報告するには、このイベント オブジェクトを送信します。 使用して、イベントが送信される、 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)は、デバッグ中のプログラムに関連付けられている場合、SDM によって指定されたコールバック関数。  
  
## <a name="remarks"></a>コメント  
 手順を完了すると、デバッグ中のプログラムがもう一度、一時停止し、すべてのウィンドウが更新されます。  
  
## <a name="requirements"></a>要件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)