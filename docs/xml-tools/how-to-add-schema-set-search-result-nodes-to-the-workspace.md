---
title: "方法: スキーマ セットの検索結果のノードをワークスペースに追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 659eaa454243dac8ac05a5f2749237944833da10
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>方法: スキーマ セットの検索結果のノードをワークスペースに追加する
このトピックでは、キーワード検索の結果、XML スキーマ エクスプローラーに強調表示されたノードをワークスペースに追加する方法について説明します。  
  
> [!NOTE]
>  グローバル ノードだけに追加することができます、[ワークスペース](../xml-tools/xml-schema-designer-workspace.md)です。  
  
 この例は、サンプルを使用して[購買発注書スキーマ](../xml-tools/sample-xsd-file-purchase-order-schema.md)です。  
  
### <a name="to-add-schema-set-result-nodes"></a>スキーマ セットの検索結果のノードを追加するには  
  
1.  手順に従います[する方法: を作成し、XSD スキーマ ファイルを編集](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)です。  
  
2.  検索 ボックスに「purchaseOrder」を入力、 [XML エクスプ ローラー](../xml-tools/xml-schema-explorer.md)ツールバーや検索ボタンをクリックします。  
  
     ![XML スキーマ エクスプ ローラー キーワード検索](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     検索結果が XML スキーマ エクスプローラーで強調表示され、垂直スクロール バーのチックでマークされます。  
  
3.  クリックして、ワークスペースに検索結果を追加、**強調表示されたノードをワークスペースに追加**概要結果ペインでボタンをクリックします。  
  
     ![XML スキーマ エクスプ ローラー検索結果](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     `purchaseOrder`ノードおよび`PurchaseOrderType`ノードがのデザイン サーフェイスに並べて表示されます、[グラフ ビュー](../xml-tools/graph-view.md)です。 2 つのノードは関連があるため (`purchaseOrder` 要素は `PurchaseOrderType` 型)、これらの間に矢印が引かれます。