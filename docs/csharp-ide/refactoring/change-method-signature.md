---
title: "メソッド シグネチャの変更 - リファクタリング (c#) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: b4f45f9d-9c8f-46ae-99f7-7705c6d90b6e
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs: csharp
ms.openlocfilehash: 9ed72704c37fcfc5d0c48ba17937f5b06097ce0b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="change-a-method-signature-in-c"></a>C# の場合、メソッド シグネチャを変更します。 #
**新機能:**を削除するか、メソッドのパラメーターの順序を変更することができます。

****を移動またはさまざまな場所で現在使用されているメソッドのパラメーターを削除します。  

**理由:**エラーにつながる可能性のあるが、手動で削除し、パラメーターの順序を変更およびそのメソッドにすべての呼び出しを検索し、1 つずつ、それらを変更します。  このリファクタリング ツールは、タスクを自動的に実行されます。

**どう：**

1. 強調表示や、カーソルを置き、テキストの名前を変更するメソッドまたはその用途の 1 つの内部。

   ![強調表示されたコード](media/changesignature_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + R**、し**ctrl キーを押しながら V**です。  選ばれているプロファイルによってキーボード ショートカットが異なる場合があることに注意してください。
     * キーを押して**Ctrl + です。** トリガーを**クイック アクションとリファクタリング**メニュー**シグネチャの変更の**プレビュー ウィンドウのポップアップからです。
   * **マウス**
     * 選択**編集 > リファクター > パラメーターを削除する**です。
     * 選択**編集 > リファクター > パラメーターを並べ替える**です。
     * コードを右クリックし、選択、**クイック アクションとリファクタリング**メニュー**シグネチャの変更の**プレビュー ウィンドウのポップアップからです。

1. **シグネチャの変更**、ポップアップ表示されるダイアログ メソッド シグネチャを変更する、右側にあるボタンを使用することができます。

   ![署名の変更 ダイアログ](media/changesignature_dialog.png)

   | ボタン | 説明
   | ------ | ---
   | **上/下** | 選択したパラメーター リストを上下に移動します。
   | **削除**  | 一覧から選択したパラメーターを削除します。
   | **復元** | 選択すると、取り消しのパラメーターを一覧に復元します。

   > [!TIP]
   > 使用して、 [**参照の変更のプレビュー** ](../../ide/preview-changes.md)にコミットする前に、結果を確認するチェック ボックスをオンします。

1. 完了したら、キーを押して、 **OK**変更を加えるボタンをクリックします。

   ![署名の結果を変更します。](media/changesignature_result.png)

## <a name="see-also"></a>関連項目  
[リファクタリング (C#)](../refactoring-csharp.md)  
[変更のプレビュー](../../ide/preview-changes.md)