---
title: "DoWhile アクティビティ デザイナー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 43a55a8873fa10fb31db89364c50e084cd72fb5c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="dowhile-activity-designer"></a>DoWhile アクティビティ デザイナー
<xref:System.Activities.Statements.DoWhile>に含まれているアクティビティを実行、<xref:System.Activities.Statements.DoWhile.Body%2A>を少なくとも 1 回に、指定した条件が評価されるまで**false**です。 ループの本体に含まれるアクティビティを 0 回以上実行する必要がある場合は、代わりに、<xref:System.Activities.Statements.While> アクティビティを使用します。  
  
## <a name="dowhile-properties-in-the-workflow-designer"></a>ワークフロー デザイナーでの DoWhile のプロパティ  
 次の表に、最も役に立つ <xref:System.Activities.Statements.DoWhile> アクティビティのプロパティと、デザイナーでのその使用方法を示します。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|条件がときに実行するアクティビティ**true**です。 追加する、<xref:System.Activities.Statements.DoWhile.Body%2A>アクティビティで、[ツールボックス] からアクティビティのドロップ、**本文**ボックスに、 **DoWhile**アクティビティ デザイナーのヒント テキストが「Drop ここにアクティビティ」です。|  
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|True|ループの各繰り返しの後に評価する条件。 設定する、 <xref:System.Activities.Statements.DoWhile.Condition%2A>、種類 a[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]内の式、**条件**ボックスに、 **DoWhile**アクティビティ デザイナーまたはプロパティ グリッドでします。|  
  
## <a name="see-also"></a>関連項目  
 [While](../workflow-designer/while-activity-designer.md)   
 [制御フロー](../workflow-designer/control-flow-activity-designers.md)