---
title: "リファクタリング (c#) - 一致するファイルの種類に移動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40f58c34-c50f-4297-91b2-2e243380dcc9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9fa5a15f9c8e688c973594309efbfa6cb5d10e8b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="move-a-type-to-a-matching-file-in-c"></a>型を c# で一致するファイルに移動します。 #
**新機能:**選択した型を同じ名前の別のファイルに移動することができます。

****を区別する、同じファイルに複数のクラス、構造体、インターフェイスなどがあります。  

**理由:**同じファイルに複数の型を配置することができますしづらくなるこれらの型を検索します。  型を同じ名前のファイルに移動して読みやすく理解しやすくするコードになります。

**どう：**

1. 強調表示や、カーソルを置き、テキスト内を移動する型の名前。

   ![強調表示されたコード](media/movetype_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + です。** トリガーに、**クイック アクションとリファクタリング**メニュー**型に移動*TypeName*.cs**プレビュー ウィンドウのポップアップから場所*TypeName* 、選択した種類の名前を指定します。
   * **マウス**
     * コードを右クリックし、選択、**クイック アクションとリファクタリング**メニュー**型に移動*TypeName*.cs**プレビュー ウィンドウから場所*TypeName*選択した種類の名前を指定します。

   種類は、すぐに、ソリューション内でその名前の新しいファイルに移動します。

   ![Inline 結果](media/movetype_result.png)

## <a name="see-also"></a>関連項目  
[リファクタリング (C#)](../refactoring-csharp.md)