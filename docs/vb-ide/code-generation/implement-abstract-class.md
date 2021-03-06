---
title: "抽象クラスのコード生成 (Visual Basic) を実装 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 68f60b6159cad7f751dfc47a8af116ef33a164c2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="implement-an-abstract-class-in-visual-basic"></a>Visual Basic では抽象クラスを実装します。
**新機能:**直ちに抽象クラスの実装に必要なコードを生成することができます。 

****抽象クラスから継承します。  

**理由:**すべて抽象メンバー 1 つずつを手動で実装でしたが、この機能では、すべてのメソッド署名を自動的に作成されます。 

**どう：**

1. 行にカーソルを置いてが抽象クラスから継承されたが、必要なすべてのメンバーを実装していないことを示す赤い波線がある場合。

   ![強調表示されたコード](media/abstract_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + です。** トリガーを**クイック アクションとリファクタリング**メニュー**抽象クラスの実装**プレビュー ウィンドウのポップアップからです。
   * **マウス**
     * 右クリックし、選択、**クイック アクションとリファクタリング**メニュー**抽象クラスの実装**プレビュー ウィンドウのポップアップからです。
     * 赤の波線をポイントし、をクリックします ![電球](media/bulb.png) 表示されるアイコン。
     * をクリックします ![電球](media/bulb.png) テキストのカーソルは赤の波線では、行に既に存在する場合、左余白に表示されるアイコン。

   ![実装クラスのプレビュー](media/abstract_preview.png)

   >[!TIP]
   >使用して、 [**変更のプレビュー** ](../../ide/preview-changes.md)をすべての選択内容を確定する前に行われる変更を表示するプレビュー ウィンドウの下部にあるリンクします。
   >
   >また、使用することができます、**ドキュメント**、**プロジェクト**、および**ソリューション**を適切なメソッドのシグネチャを複数作成するプレビュー ウィンドウの下部にあるリンク抽象クラスから継承するクラス。

1. 抽象メソッドのシグネチャは、自動的に作成された、実装する準備完了になります。

   ![クラスの結果を実装します。](media/abstract_result.png)

## <a name="see-also"></a>関連項目  
[コード生成 (Visual Basic)](../code-generation-vb.md)  
[変更のプレビュー](../../ide/preview-changes.md)