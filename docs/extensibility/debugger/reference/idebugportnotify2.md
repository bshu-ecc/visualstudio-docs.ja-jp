---
title: "IDebugPortNotify2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortNotify2
helpviewer_keywords:
- IDebugPortNotify2 interface
ms.assetid: 43278b79-bf16-4c08-bcf1-6f7f7a17feab
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: de163fdf55052ff4cc2f1599bc8ddfd162d03df3
ms.lasthandoff: 04/05/2017

---
# <a name="idebugportnotify2"></a>IDebugPortNotify2
このインターフェイスは、登録またはで実行されているポートとデバッグ可能なプログラムの登録を解除します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugPortNotify2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 カスタム ポート仕入先では、サポートを追加して、ポートからプログラムを削除するのには、このインターフェイスを実装します。 通常、同じオブジェクトを実装するに実装されている、 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)インターフェイスです。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出し[QueryInterface](/cpp/atl/queryinterface)上、`IDebugPort2`インターフェイスは、このインターフェイスを返します。 呼び出しも、 [GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)このインターフェイスを返します。 デバッグ エンジンは、このインターフェイスを参照してへのパラメーターとして[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)です。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDebugPortNotify2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)|実行されているポートをデバッグできるプログラムを登録します。|  
|[RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)|実行されているポートからデバッグできるプログラムの登録を解除します。|  
  
## <a name="remarks"></a>コメント  
 デバッグ ポートは、プログラムがロードまたはアンロードされたときを知る手段を持つ、しない限り、カスタム ポートのサプライヤーは、このインターフェイスを実装する必要があります。 特定のポートを使用して、デバッグに読み込まれるすべてのプログラムは、このインターフェイスを使用して追跡されます。  
  
## <a name="requirements"></a>要件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)