---
title: "Visual Studio での Python の使用、手順 4 | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: d76f8d93-30f4-424e-be90-0765d036c816
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: a70973e4b7da01e6718922958e0ba8013b421af8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="step-4-running-code-in-the-debugger"></a>手順 4: デバッガーでコードを実行する

**前の手順: [対話型 REPL ウィンドウを使用する](vs-tutorial-01-03.md)**

Visual Studio は、プロジェクト管理、豊富な編集機能、対話型ウィンドウに加え、Python コードを完全にデバッグする機能も提供しています。 デバッガーでは、ループのすべてのイテレーションを含め、コードをステップ実行できます。 また、特定の条件に当てはまるとき、プログラムを一時停止することもできます。 デバッガーによって任意の時点でプログラムが一時停止された場合、プログラム全体の状態を確認して変数の値を変更できます。 そのような操作は、プログラムのバグを追跡するために必須です。また、プログラムの正確なフローを理解するのに、非常に便利です。

1. `PythonApplication1.py` ファイル内のコードを次に置き換えます。 このコードのバリエーションが `make_dot_string` を展開し、デバッガーで個別のステップを調べることができるようになります。 また、これは `main` 関数に `for` ループを配置し、その関数を呼び出してそれを明示的に実行します。

    ```python  
    import sys  
    from math import sin, cos, radians    
    
    # Create a string with spaces proportional to a cosine of x in degrees
    def make_dot_string(x):
        rad = radians(x)                             # cos works with radians
        numspaces = int(20 * cos(radians(x)) + 20)   # scale to 0-40 spaces
        str = ' ' * numspaces + 'o'                  # place 'o' after the spaces
        return str
    
    def main():  
        for i in range(0, 1800, 12):
            s = make_dot_string(i)  
            print(s)  
            
    main()
    ```  

1. コードが正常に機能することを確認します。それには、F5 キーを押すか、または **[デバッグ] > [デバッグの開始]** メニュー コマンドを選択します。 このコマンドにより、デバッガーでコードが実行されますが、実行中のプログラムを停止する設定はないので、数回のイテレーションの波のパターンが単純に出力されます。 キーを押すと出力ウィンドウに出力されます。

    > [!Tip]
    > プログラムが完了したときに出力ウィンドウを自動的に閉じるには、`main()` の呼び出しを次のコードに置き換えます。
    >
    > ```python    
    > if __name__ == "__main__":  
    >     sys.exit(int(main() or 0))      
    > ```    

1. `for` ステートメントにブレークポイントを設定します。それには、行の灰色の余白を一度クリックするか、行にキャレットを配置して **[デバッグ] > [ブレークポイントの設定/解除]** コマンドを使用します (または F9 キーを押します)。 灰色の余白に、ブレークポイントを示す赤い点が表示されます (下図の矢印の先)。

    ![ブレークポイントの設定](media/vs-getting-started-python-18-debugging1.png)

1. デバッガーをもう一度開始 (F5) すると、ブレークポイントを設定した行でコードの実行が停止します。 ここで、呼び出し履歴を確認したり、変数を調べたりすることができます。 スコープ内の変数が定義されている場合、**[自動変数]** ウィンドウに表示されます。このウィンドウの下の **[ローカル]** ビューに切り替え、Visual Studio が現在のスコープ (関数も含む) で見つけたすべての変数を定義前でも表示することができます。

    ![Python のブレークポイント UI エクスペリエンス](media/vs-getting-started-python-19-debugging2b.png)

1. Visual Studio ウィンドウの上部にある、デバッグ ツールバー (下記参照) を確認します。 このツールバーからは、最も一般的なデバッグ コマンド (これは **[デバッグ]** メニューにもあります) に迅速にアクセスできます。

    ![基本のデバッグ ツール バー ボタン](media/vs-getting-started-python-20-debugging3.png)

    左から右にボタンを説明します。
    - **[続行]** (F5): 次のブレークポイントまたはプログラムの完了までプログラムを実行します。
    - **[すべて中断]** (Ctrl + Alt + Break): 実行時間の長いプログラムを一時停止します。
    - **[デバッグの停止]** (Shift + F5): その場でプログラムを停止し、デバッガーを終了します。
    - **[再起動]** (Ctrl + Shift + F5): その場でプログラムを停止し、デバッガーで最初から再開します。
    - **[次のステートメントの表示]** (Alt + Num *): 実行するコードを次の行に切り替えます。 これは、デバッグ セッション中に、コード内を移動するときに、デバッガーが一時停止しているところにすばやく戻りたい時に一番役立ちます。
    - **[ステップ イン]** (F11): コードの次の行を実行し、呼び出された関数に入ります。
    - **[ステップ オーバー]** (F10): 呼び出された関数には入らずに、コードの次の行を実行します。
    - **[ステップ アウト]** (Shift + F11): 現在の関数の残りの部分を実行し、呼び出し元のコードで一時停止します。

1. **[ステップ オーバー]** を使用し、`for` ステートメントをステップ オーバーします。 *ステップ実行*とは、デバッガーがすべての関数呼び出しを含む現在のコード行を実行し、またすぐに一時停止することを意味します。 変数 `i` が現在、**[ローカル]** および **[自動変数]** ウィンドウでどのように定義されているか確認してください。
 
1. 次のコード行をステップ オーバーし、`make_dot_string` を呼び出し、一時停止します。 ここでのステップ オーバーとは、デバッガーが `make_dot_string` 全体を実行し、戻るときに一時停止することを意味します。 そこに別のブレークポイントがある場合を除き、デバッガーはその関数内では停止しません。

1. コードをあと数回ステップ オーバーし、**[ローカル]** または **[自動変数]** ウィンドウの値がどのように変わるか確認します。

1. **[ローカル]** または **[自動変数]** ウィンドウで、値を編集するために `i` または `s` 変数のいずれかの **[値]** 列でダブルクリックします。 変更する場合、Enter を押すか、値の外でクリックし、それを適用します。

1. **[ステップ イン]** を使用して、コードのステップ実行を続行します。 ステップ インとは、`make_dot_string` など、デバッグ情報がある任意の関数呼び出しにデバッガーが入ることを意味します。 `make_dot_string` の中に一度入ると、そのローカル変数を確認し、そのコードを明確にステップ実行できます。
 
1. ステップ インを使用してステップ実行を継続します。`make_dot_string` の終わりに到達すると、次のステップでは `for` ループに戻ることに注意してください。このとき、`s` 変数には新しい戻り値があります。 再度 `print` ステートメントにステップ実行すると、`print` に対するステップ インではその関数には入りません。 これは、`print` が Python ランタイムのネイティブ コードであり、Python に書き込まれていないためです。

1. また `make_dot_string` の中に入るまで、ステップ インの使用を続けます。 次いで **[ステップ アウト]** を使用し、`for` ループに戻ることを確認します。 ステップ アウトでは、デバッガーは関数の残りの部分を実行し、呼び出し元のコードで自動的に一時停止します。 デバッグする長い関数の一部をステップ実行したが、残りはステップ実行する必要がない場合、また呼び出し元のコードで明示的にブレークポイントを設定しない場合、これは非常に便利です。

1. 次のブレークポイントに到達するまで、プログラムの実行を続けるには、**[続行]** (F5) を使用します。 `for` ループにブレークポイントを設定しているので、次のイテレーションで中断します。

1. ループのイテレーションを何百回もステップ実行することは面倒なため、Visual Studio では、ブレークポイントに*条件*を追加できます。 これを使用すると、デバッガーは条件が満たされた場合のみ、ブレークポイントでプログラムを停止します。 たとえば、`for` ステートメントにブレークポイントがある条件を使用し、`i` の値が 1600 を超えた場合のみ一時停止するようにできます。 この条件を設定するには、ブレークポイントの赤い点を右クリックして **[条件]** を選択します(Alt + F9、C)。 表示された **[ブレークポイント設定]** ポップアップで、式として `i > 1600` と入力し、**[閉じる]** を選択します。 F5 キーを押して続行し、次の改行までプログラムが多数のイテレーションを実行することを確認します。 

    ![ブレークポイント条件の設定](media/vs-getting-started-python-21-debugging4.png)

1. 完了までプログラムを実行するには、**[ブレークポイントの無効化]** を右クリックして選択して (Ctrl + F9)、ブレークポイントを無効にします。 次いで **[続行]** を選択し (または F5 キーを押して)、プログラムを実行します。 プログラムが終了すると、Visual Studio は、デバッグ セッションを停止し編集モードに戻ります。 そのドットをクリックして、ブレークポイントを削除することもできますが、これにより、設定した任意の条件も削除されることに注意してください。

> [!Tip]    
> Python インタープリター自体の起動に失敗した場合など、出力ウィンドウがごく短時間表示され、自動的に閉じてしまい、エラー メッセージが表示されない場合があります。 これが起こった場合、ソリューション エクスプローラーでプロジェクトを右クリックし、**[プロパティ]** の **[デバッグ]** タブを選び、**[インタープリター引数]** フィールドに `-i` を追加します。 この引数により、プログラム完了後にインタープリターは対話モードになり、ユーザーが Ctrl + Z キー、Enter キーの順に押して終了するまで、ウィンドウは開いたままになります。

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [Python 環境へのパッケージのインストール](vs-tutorial-01-05.md)

### <a name="going-deeper"></a>詳しい説明
- [デバッグ](debugging.md)
- 「[Visual Studio でのデバッグ](../debugger/debugging-in-visual-studio.md)」では、Visual Studio のデバッグ機能が完全に説明されています。