---
title: "変更のプレビュー | Microsoft ドキュメント"
ms.custom: 
ms.date: 12/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e15c00f6-3e22-49b8-8269-69e4c8be8040
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.codefix.previewchanges
ms.openlocfilehash: 52555d0bc112dae41f189fd9f29711da365fd59c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="preview-changes"></a>変更のプレビュー

Visual Studio でさまざまな*クイック アクション* ツールまたは*リファクタリング* ツールを使用すると、実施される変更を受け入れる前にプレビューできることがよくあります。  プレビューは、**[変更のプレビュー]** で行います。  たとえば、ここでは、C# プロジェクトにおける名前の変更リファクタリング中に変更される内容が **[変更のプレビュー]** に表示されています。

![変更のプレビュー](media/previewchanges.png)

ウィンドウの上半分には、変更される特定の行が表示され、それぞれの行にチェックボックスが配置されています。  特定の行にのみ選択的にリファクタリングを適用する場合は、各チェック ボックスをオフまたはオフにします。

ウィンドウの下半分には、変更されるプロジェクトからの書式設定されたコードが表示され、影響を受ける部分が強調表示されています。  ウィンドウの上半分で特定の行を選択すると、ウィンドウの下半分で対応する行が強調表示されます。  これにより、該当する行にすばやくスキップして、前後のコードを確認することができます。

変更内容を確認したら、**[適用]** ボタンをクリックして該当する変更をコミットするか、**[キャンセル]** をクリックして元のままにしておきます。

## <a name="see-also"></a>関連項目  
[Visual Studio でのリファクタリング](../ide/refactoring-in-visual-studio.md)
