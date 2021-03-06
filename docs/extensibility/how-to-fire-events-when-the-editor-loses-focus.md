---
title: "方法: エディターがフォーカスを失ったときにイベントを発生させる |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9a566d52dc1aabb9895e2f1f9751fdb37ae016d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>方法: エディターがフォーカスを失ったときにイベントを発生させる
エディターは、ウィンドウ フレームにフォーカスを失ったときに知っておく必要があります。 たとえば、エディターが不要になったことにフォーカスが移動した後に、コード ウィンドウからコードを抽出する必要があります。 次の手順では、フォーカスを失うエディターの通知を受信するために従う手順を説明します。  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>フォーカスを失うエディターへの応答でイベントを発生させる  
  
1.  取得することによって選択イベントを監視、<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>オブジェクトから<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>です。  
  
2.  呼び出す<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A>提供して、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>オブジェクト。  
  
3.  呼び出しで<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>、探します`elementid==SEID_WindowFrame`です。  
  
4.  テスト、`varValueNew`次の 2 つのパラメーター。  
  
    1.  探しているウィンドウ フレームです。  
  
    2.  プログラムがウィンドウ フレームに選択範囲を失うをポイントします。