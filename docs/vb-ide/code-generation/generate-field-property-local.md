---
title: "フィールド、プロパティ、またはローカル - コード生成 (Visual Basic) を生成します |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2dd0ef0db74a0ee723c7cd09bd8118e646b8ba3f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="generate-a-field-property-or-local-in-visual-basic"></a>Visual Basic でのフィールド、プロパティ、またはローカルを生成します。
**新機能:**すぐに以前に宣言されていないフィールド、プロパティ、またはローカルのコードを生成することができます。 

****入力中に、新しいフィールド、プロパティ、またはローカルを導入して、自動的に正しく宣言します。  

**理由:**が、この機能は、宣言を生成し、自動的に入力し、使用する前に、フィールド、プロパティ、またはローカルを宣言することができます。 

**どう：**

1. 行にカーソルを置いて、ローカルのフィールドを使用したことを示す赤い波線やがまだ存在しないプロパティがある場合。

   ![強調表示されたコード](media/field_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + です。** トリガーを**クイック アクションとリファクタリング**メニューを選択**生成変数 '*名前*' > フィールド/プロパティを生成/ローカル * * プレビュー ウィンドウのポップアップからです。
   * **マウス**
     * 右クリックし、選択、**クイック アクションとリファクタリング**メニュー **生成変数 '*名前*' > フィールド/プロパティの生成/ローカル * *、プレビューからウィンドウのポップアップ。
     * 赤の波線をポイントし、をクリックします ![電球](media/bulb.png) 表示されるアイコン。
     * をクリックします ![電球](media/bulb.png) テキストのカーソルは赤の波線では、行に既に存在する場合、左余白に表示されるアイコン。

   ![フィールド/プロパティ/ローカルのプレビューを生成します。](media/field_preview.png)

   >[!TIP]
   >使用して、 [**変更のプレビュー** ](../../ide/preview-changes.md)をすべての選択内容を確定する前に行われる変更を表示するプレビュー ウィンドウの下部にあるリンクします。

1. フィールド、プロパティ、またはローカルは、その使用法から推論された型に自動的に作成されます。

   ![フィールド/プロパティ/ローカルの結果を生成します。](media/field_result.png)

## <a name="see-also"></a>関連項目  
[コード生成 (Visual Basic)](../code-generation-vb.md)  
[変更のプレビュー](../../ide/preview-changes.md)