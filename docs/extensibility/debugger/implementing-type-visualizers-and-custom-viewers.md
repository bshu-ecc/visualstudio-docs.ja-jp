---
title: "ビジュアライザーの型およびカスタム ビューアーを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: abef18c0-8272-4451-b82a-b4624edaba7d
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 19718425df6f0c8a656db0e3d7ebf0f06937f780
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-type-visualizers-and-custom-viewers"></a>ビジュアライザーの型およびカスタム ビューアーを実装します。
> [!IMPORTANT]
>  Visual Studio 2015 では、式エバリュエーターを実装するには、この方法は推奨されなくなりました。 CLR 式エバリュエーターを実装する方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)です。  
  
 ビジュアライザーの型とカスタム ビューアーは、数値の単純な 16 進数のダンプよりもわかりやすい方法で特定の種類のデータを表示するユーザーを許可します。 式エバリュエーター (EE) は、カスタム ビューアーを特定の種類のデータまたは変数に関連付けることができます。 これらのカスタム ビューアーは、EE によって実装されます。 EE は、外部型のビジュアライザーは、他のサード パーティ ベンダーまたはエンドユーザーでもから取得する可能性がありますもサポートできます。  
  
## <a name="discussion"></a>説明  
  
### <a name="type-visualizers"></a>ビジュアライザーの型  
 Visual Studio では、[ウォッチ] ウィンドウに表示するには、ビジュアライザーの型とすべてのオブジェクトへのカスタム ビューアーの一覧を要求します。 式エバリュエーター (EE) は、ビジュアライザーの型とカスタム ビューアーをサポートするかの種類ごと、そのようなリストを指定します。 呼び出す[GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)と[GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)型ビジュアライザーとカスタム ビューアーにアクセスするプロセス全体を開始 (を参照してください[Visualizing とデータの表示](../../extensibility/debugger/visualizing-and-viewing-data.md)詳細については、呼び出し元のシーケンスで)。  
  
### <a name="custom-viewers"></a>カスタム ビューアー  
 カスタム ビューアーが特定のデータ型の EE で実装され、によって表される、 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)インターフェイスです。 カスタム ビューアー柔軟性は高くありませんとして型のビジュアライザーでは、その特定のカスタム ビューアーを実装する EE を実行する場合にのみが使用できるためです。 カスタム ビューアーを実装することは、ビジュアライザーの型のサポートを実装するよりも簡単です。 ただし、種類のビジュアライザーをサポートする柔軟性が最大をエンドユーザーに自分のデータの視覚化。 このディスカッションの残りの部分では、型のビジュアライザーだけに関するものです。  
  
## <a name="interfaces"></a>インターフェイス  
 EE は、型のビジュアライザーを Visual Studio での使用をサポートするために、次のインターフェイスを実装します。  
  
-   [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)  
  
-   [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md)  
  
-   [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md)  
  
-   [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md)  
  
-   [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md)  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
 EE は、ビジュアライザーの型をサポートするために次のインターフェイスを使用します。  
  
-   [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)  
  
-   [IEEVisualizerServiceProvider](../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)  
  
-   [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md)  
  
## <a name="see-also"></a>関連項目  
 [CLR 式エバリュエーターの書き込み](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [視覚化とデータを表示します。](../../extensibility/debugger/visualizing-and-viewing-data.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)