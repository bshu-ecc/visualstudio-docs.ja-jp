---
title: "インライン一時変数のリファクタリング (Visual Basic) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a63d6407-5acb-4d5f-8c0e-ecedddc07177
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 574a1a41464ede08571e1c0201618d666fa7ad92
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>インライン Visual Basic での一時変数
**新機能:**する一時変数の使用を削除し、代わりに実際のコードに置き換えることができます。

****一時変数の使用により、コードの理解が困難になります。  

**理由:**一時変数を削除することによりコードを特定の状況で読みやすくします。

**どう：**

1. 強調表示またはインライン展開を解除する一時変数内のテキストのカーソルを置きます。

   ![強調表示されたコード](media/inline_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + です。** トリガーを**クイック アクションとリファクタリング**メニュー**インライン一時変数**プレビュー ウィンドウのポップアップからです。
   * **マウス**
     * コードを右クリックし、選択、**クイック アクションとリファクタリング**メニュー**インライン一時変数**プレビュー ウィンドウのポップアップからです。

   変数は削除されますされ、その用途がすぐに、変数の値で置き換えられます。

   ![Inline 結果](media/inline_result.png)

## <a name="see-also"></a>関連項目
[リファクタリング (Visual Basic)](../refactoring-vb.md)