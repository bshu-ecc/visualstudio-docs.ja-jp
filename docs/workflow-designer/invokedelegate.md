---
title: "InvokeDelegate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
caps.latest.revision: "3"
ms.author: sdanie
manager: erikre
ms.openlocfilehash: 180e9ca5ae635608ca3d7f9cf24abab13c8076a6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="invokedelegate"></a>InvokeDelegate
**InvokeDelegate**デザイナーを使用して作成し、構成、<xref:System.Activities.Statements.InvokeDelegate>アクティビティ。  
  
## <a name="the-invokedelegate-activity"></a>InvokeDelegate アクティビティ  
 <xref:System.Activities.Statements.InvokeDelegate> はパブリック デリゲートを呼び出します。  
  
### <a name="using-the-invokedelegate-activity-designer"></a>InvokeDelegate アクティビティ デザイナーの使用  
 **InvokeDelegate**アクティビティ デザイナーは含まれて、**プリミティブ**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス**タブ[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)](または、選択**ツールバー**から、**ビュー**  メニューまたは CRTL + ALT + X です)。  
  
 **InvokeDelegate**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**に、[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]画面でアクティビティを通常配置など内、<xref:System.Activities.Statements.Sequence>です。 この操作により、InvokeDelegate という既定の <xref:System.Activities.Statements.InvokeDelegate> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 <xref:System.Activities.Activity.DisplayName%2A>のヘッダーで編集できる、 **InvokeDelegate**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。  
  
### <a name="the-invokedelegate-properties"></a>InvokeDelegate プロパティ  
 次の表に、<xref:System.Activities.Statements.InvokeDelegate> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドで編集できます。また、その一部は[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]のデザイナー画面で編集できます。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> アクティビティの表示名。 既定値は InvokeDelegate です。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|  
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|アクティビティの実行時に呼び出す <xref:System.Activities.ActivityDelegate> の名前。 このプロパティは、デザイナー画面で設定することもできます。 これは必須プロパティです。|  
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|呼び出されたデリゲートの引数コレクション。 キーのパラメーター オブジェクトの名前は、<xref:System.Activities.ActivityDelegate>値は、引数の式が評価され、対応するパラメーター オブジェクトに割り当てられているとします。 プロパティ グリッドでの省略記号ボタンをクリックして、 **DelegateArguments**フィールドが表示されます、 **DelegateArguments**ダイアログ ボックスをこのプロパティを設定できます。 クリックして、**引数の作成**引数を追加するフィールドです。|  
  
## <a name="see-also"></a>関連項目  
 [方法: ワークフロー デザイナーでアクティビティ デリゲートを定義および使用する](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)