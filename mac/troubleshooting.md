---
title: "トラブルシューティング"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: CE860D79-E29E-4B93-B094-BE74B35FC1C2
ms.translationtype: HT
ms.sourcegitcommit: e2b7ff9126e1cc38ac2e58d6be339b656a024e7f
ms.openlocfilehash: a820423704b6f656b55b7e33f15d1c7880d2e27d
ms.contentlocale: ja-jp
ms.lasthandoff: 08/11/2017

---

# <a name="troubleshooting"></a>トラブルシューティング

## <a name="viewing-logs-in-visual-studio-for-mac"></a>Visual Studio for Mac でのログを表示する
 
ログは、**[ヘルプ] > [ログ ディレクトリを開く]** メニュー項目で見ることができます (下図参照)。

![[ログ ディレクトリを開く] メニュー項目](media/troubleshooting-image1.png)

## <a name="viewing-exceptions"></a>例外を表示する

例外がキャッチされると、例外バブルが表示されます。 詳細を表示するには、**[詳細の表示]** ボタンを選びます。

![例外に関する詳細情報を表示する](media/troubleshooting-image2.png)

**[詳細の表示]** ダイアログが開き、例外に関する詳細情報が表示されます。

![](media/troubleshooting-image3.png)

ダイアログの重要なセクションについて以下で詳しく説明します。番号は上の図に対応しています。

1. 例外の種類。検出された例外の種類の完全な名前を示します。
2. 例外メッセージ。例外オブジェクトの Message プロパティの値を示します。
3. 内部例外の種類。現在選択されている例外の内部例外ツリー ビューでの例外の種類の完全な名前を示します。
4. 内部例外メッセージ。選択されている例外の内部例外ツリー ビューでの Message プロパティの値を示します。
5. StackTrace ビュー。 表示矢印で折りたたむことができ、スタック フレームのエントリが含まれます。
6. 非ユーザー コード エントリの例。
7. ユーザー コード エントリの例。
8. プロパティ ビュー。例外のすべてのプロパティとフィールドが表示されます。 表示矢印を使って折りたたむことができます。
9. 内部例外ツリー ビュー。 キーボードの上/下方向キー、マウス、またはトラックパッドを使って、このビューで内部例外を選びます。
10. 既定では、これはデバッガー設定の **[プロジェクト コードのみをデバッグします]** オプションの設定に設定されます。 このボックスをオンにすると、すべての非ユーザー コードを StackTrace の 1 つの行に折りたたむことができます。
11. コピー ボタン。`exception.ToString()` の出力をクリップボードにコピーします。

これらのセクションの一部は、例外が内部例外である場合にのみ表示されることに注意してください。