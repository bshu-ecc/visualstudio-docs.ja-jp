---
title: "CorrelationScope アクティビティ デザイナー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.ServiceModel.Activities.CorrelationScope.UI
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3e6e745e470c5e5b5a279f460198729bd9429ccc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="correlationscope-activity-designer"></a>CorrelationScope アクティビティ デザイナー
**CorrelationScope**アクティビティ デザイナーを使用して作成し、構成、<xref:System.ServiceModel.Activities.CorrelationScope>暗黙で管理を使用して、子メッセージング アクティビティのアクティビティ、<xref:System.ServiceModel.Activities.CorrelationHandle>オブジェクト。  
  
## <a name="the-correlationscope-activity"></a>CorrelationScope アクティビティ  
 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> プロパティでは、子メッセージング アクティビティの管理に使用する <xref:System.ServiceModel.Activities.CorrelationHandle> を指定します。 <xref:System.ServiceModel.Activities.Send> に含まれる <xref:System.ServiceModel.Activities.Receive> アクティビティおよび <xref:System.ServiceModel.Activities.CorrelationScope.Body%2A> アクティビティは、親 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> アクティビティの <xref:System.ServiceModel.Activities.CorrelationScope> プロパティを使用して関連付けを行うように構成されます。  
  
### <a name="using-the-correlationscope-activity-designer"></a>CorrelationScope アクティビティ デザイナーの使用  
 **CorrelationScope**アクティビティ デザイナーは含まれて、**メッセージング**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス**  タブの左側にある、 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (または、選択**ツールバー**から、**ビュー**メニューのまたは CTRL + ALT + X です)。  
  
 **CorrelationScope**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**に、[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]画面。 これを作成、 <xref:System.ServiceModel.Activities.CorrelationScope> 、既定値を持つアクティビティ**DisplayName** CorrelationScope のです。 <xref:System.Activities.Activity.DisplayName%2A>のヘッダーで編集できる、 **CorrelationScope**アクティビティ デザイナーまたは、 **DisplayName**のボックス、**プロパティ**ウィンドウです。  
  
 指定する、<xref:System.ServiceModel.Activities.CorrelationHandle>の横にある省略記号ボタンをクリックして、子メッセージング アクティビティを使用して、 **CorrelatesWith**フィールドに**プロパティ**ウィンドウに表示する、**式エディター**  ダイアログ ボックス。 このプロパティは、アクティビティ デザイナー画面で設定することもできます。  
  
 相関関係のスコープ内でアクティビティがデザイナーをドロップすることによって指定された、**本文**ボックス内、 **CorrelationScope**デザイナー。  
  
### <a name="the-correlationscope-properties"></a>CorrelationScope プロパティ  
 次の表に、<xref:System.ServiceModel.Activities.CorrelationScope> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティのどちらでも編集**プロパティ**ウィンドウまたは[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]デザイナー画面で、多くの場合、両方でします。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.InitializeCorrelation> アクティビティの省略可能な表示名。|  
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|子メッセージング アクティビティの管理に使用する <xref:System.ServiceModel.Activities.CorrelationHandle> を指定します。 このプロパティを設定しない場合は、<xref:System.ServiceModel.Activities.CorrelationScope> に、暗黙の <xref:System.ServiceModel.Activities.CorrelationHandle> が自動的に作成されます。|  
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|相関関係のスコープ内のアクティビティを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [受信](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [送信](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)