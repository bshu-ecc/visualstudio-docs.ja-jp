---
layout: LandingPage
title: "Visual Studio でのアプリのデバッグ | Microsoft Docs"
description: "Visual Studio 2017 を使用して、ご使用のプラットフォームとデバイス向けに任意の言語でアプリケーション、サービス、ツールをデバッグする方法について説明します。"
ms.technology: vs-ide-debug
ms.openlocfilehash: d00ef04d3d8f73b607c91f33f9af53429666ba5f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-in-visual-studio"></a>Visual Studio でのデバッグ

Visual Studio デバッガーを使用すると、プログラムの実行時の動作を確認し、問題を見つけることができます。 デバッガーは、すべての Visual Studio のプログラミング言語と関連ライブラリと連携します。 デバッガーを使ってプログラムの実行を中断し、コードのチェック、変数のチェックと編集、レジスタの確認、ソース コードで作成された命令の表示、アプリケーションで使用するメモリ空間の確認などができます。

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/debugger-feature-tour">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_road-map.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>デバッガーの機能ツアー</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/getting-started-with-the-debugger">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_debug.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>デバッガーの使用開始</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/navigating-through-code-with-the-debugger">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_debug.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>デバッガーでのコードの移動</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
        <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/getting-started-with-the-debugger#video">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_video.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>デバッガーの使用方法のビデオを見る</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/remote-debugging">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_learn-about.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>リモート デバッグの詳細</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/get-started-debugging-multithreaded-apps">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_get-started.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>マルチスレッド アプリのデバッグ</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
        <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/intellitrace">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_learn-about.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>IntelliTrace の詳細 (Visual Studio Enterprise)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/debugger-tips-and-tricks">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_debug.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>デバッガーのヒントと秘訣</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/what-s-new-for-the-debugger-in-visual-studio">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/en-us/media/common/i_whats-new.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>「デバッガーの新機能」を参照してください</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

<hr>
<h2>参照</h2>

<ul class="panelContent cardsW">
    <li>
        <a href="https://msdn.microsoft.com/en-us/library/ee661590.aspx">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>IntelliTrace リファレンス</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Debug Interface Access SDK</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/en-us/visualstudio/debugger/spy-increment-help">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Spy++</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

---