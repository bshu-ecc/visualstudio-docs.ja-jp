---
title: "IDebugExceptionEvent2::PassToDebuggee |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExceptionEvent2::PassToDebuggee
helpviewer_keywords: IDebugExceptionEvent2::PassToDebuggee
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4abb59c9bf9717089353683087c38425d3bf88ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexceptionevent2passtodebuggee"></a>IDebugExceptionEvent2::PassToDebuggee
例外を破棄する必要がある場合または実行が再開したときにデバッグするプログラムを例外を渡す必要があるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```csharp  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fPass`  
 [in]0 以外 (`TRUE`) 場合は、例外は、実行が再開されるとときに、デバッグするプログラムまたはゼロ渡す必要があります (`FALSE`) 場合は、例外を破棄する必要があります。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 このメソッドを呼び出すことも、デバッグ中のプログラムで実行するためのコードは実際には発生しません。 呼び出しは、次のコード実行の状態を設定するだけです。 たとえば、呼び出し、 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)メソッドが返す可能性があります`S_OK`で、 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)です。`dwState` フィールドに設定`EXCEPTION_STOP_SECOND_CHANCE`です。  
  
 IDE が表示される、 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)イベントと呼び出し、[続行](../../../extensibility/debugger/reference/idebugprogram2-continue.md)メソッドです。 デバッグ エンジン (DE) 場合を処理する既定の動作を持つ必要があります、`PassToDebuggee`メソッドは呼び出されません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprogram2-continue.md)