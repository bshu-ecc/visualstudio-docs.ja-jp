---
title: "IDebugProgram2::Terminate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::Terminate
helpviewer_keywords: IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 16f9e718eaebbb1ab82ea96c08661622ef7e1cd1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
プログラムを終了します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT Terminate(   
   void   
);  
```  
  
```csharp  
int Terminate();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 可能であれば、プログラムは終了し、プロセスからアンロードそれ以外の場合、デバッグ エンジン (DE) は、必要なクリーンアップを実行します。  
  
 このメソッドまたは[Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)メソッドがすべてのデバッグを停止する、ユーザーへの応答では通常、IDE によって呼び出されます。 このメソッドの実装では、プロセス内でプログラムを終了する、ことをお勧めします。 これが可能でない場合、DE 必要があります、プログラムがこのプロセスでこれ以上実行するを防ぎます (および、必要なクリーンアップ操作を行います)。 場合、`IDebugProcess2::Terminate`メソッドは、IDE によって呼び出された、プロセス全体は終了の後に、`IDebugProgram2::Terminate`メソッドが呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [終了](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)