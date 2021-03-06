---
title: "方法: WCF サービスにステップ イン |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aeaba831bb82731ae7d3e62cbff5190bb474357
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-step-into-wcf-services"></a>方法 : WCF サービスにステップ インする
[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] では、WCF サービスにステップ インできます。 WCF サービスがクライアントと同じ [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ソリューションにある場合、WCF サービス内のブレークポイントに到達できます。  
  
 ステップ実行を使用するには、app.config ファイルまたは Web.config ファイルでデバッグを有効にする必要があります。 デバッグを有効にし、WCF サービスへのステップ イン制限については、次を参照してください。 方法については[WCF デバッグの制約](../debugger/limitations-on-wcf-debugging.md)です。  
  
### <a name="to-step-into-a-wcf-service"></a>WCF サービスにステップ インするには  
  
1.  WCF クライアント プロジェクトと WCF サービス プロジェクトの両方を含む [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ソリューションを作成します。  
  
2.  ソリューション エクスプ ローラーで、WCF クライアント プロジェクトを右クリックし、をクリックして**スタートアップ プロジェクトとして設定**です。  
  
3.  app.config ファイルまたは web.config ファイルでデバッグを有効にします。 詳細については、次を参照してください。 [WCF デバッグの制約](../debugger/limitations-on-wcf-debugging.md)です。  
  
4.  クライアント プロジェクト内の、ステップ実行を開始する位置にブレークポイントを設定します。 通常、これは WCF サービス呼び出しの直前です。  
  
5.  ブレークポイントまで実行した後、ステップ実行を開始します。 デバッガーがサービスに自動的にステップ インします。  
  
## <a name="see-also"></a>関連項目  
 [WCF サービスのデバッグ](../debugger/debugging-wcf-services.md)   
 [WCF のデバッグに関する制限事項](../debugger/limitations-on-wcf-debugging.md)   
 [方法 : セルフホストされている WCF サービスをデバッグする](../debugger/how-to-debug-a-self-hosted-wcf-service.md)