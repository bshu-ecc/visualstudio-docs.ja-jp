---
title: "[全般] ([オプション] ダイアログ ボックス - [デバッグ]) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.options.General"
  - "VS.ToolsOptionsPages.Debugger.General"
  - "VS.ToolsOptionsPages.Debugger.ENC"
  - "vs.debug.options.ENC"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
helpviewer_keywords: 
  - "[オプション] ダイアログ ボックス、デバッグ"
ms.assetid: b33aee0b-43c3-4c26-8ed4-bc673f491503
caps.latest.revision: 46
caps.handback.revision: 43
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# [全般] ([オプション] ダイアログ ボックス - [デバッグ])
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**\[ツール\]、\[オプション\]、\[デバッグ\]、\[全般\]** のページで、以下のオプションを設定できます。  
  
 **すべてのブレークポイントを削除する前に確認する**  
 **\[すべてのブレークポイントの削除\]** を実行する前に確認を要求します。  
  
 **\[1 つのプロセスがブレークするとき、他のプロセスもブレークする\]**  
 中断が生じると、デバッガーがアタッチされているすべてのプロセスを同時に中断します。  
  
 **\[例外が AppDomain またはマネージ\/ネイティブの境界を越える場合にブレークする\]**  
 マネージ コードのデバッグまたは混合モードのデバッグでは、次のような条件が満たされた場合、共通言語ランタイムにより、アプリケーション ドメインの境界、またはマネージ コードとネイティブ コードの境界を越える例外がキャッチされます。  
  
 1\) ネイティブ コードが、COM 相互運用機能を使用してマネージ コードを呼び出し、呼び出されたマネージ コードが例外をスローした場合。 「[Introduction to COM Interop](/dotnet/visual-basic/programming-guide/com-interop/introduction-to-com-interop)」を参照してください。  
  
 2\) アプリケーション ドメイン 1 で実行中のマネージ コードがアプリケーション ドメイン 2 のマネージ コードを呼び出し、アプリケーション ドメイン 2 のコードが例外をスローした場合。 「[アプリケーション ドメインを使用したプログラミング](http://msdn.microsoft.com/ja-jp/bd36055b-56bd-43eb-b4d8-820c37172131)」をご覧ください。  
  
 3\) コードがリフレクションを使用して関数を呼び出し、呼び出された関数が例外をスローした場合。 「[リフレクション](../Topic/Reflection%20in%20the%20.NET%20Framework.md)」を参照してください。  
  
 2\) および 3\) の場合、スローされる例外は、共通言語ランタイムではなく、`mscorlib` のマネージ コードによりキャッチされることがあります。 このオプションを選択しても、`mscorlib` でキャッチされる例外の処理は中断されません。  
  
 **アドレスレベルのデバッグを有効にする**  
 アドレス レベルでデバッグを行うための高度な機能 \( **\[逆アセンブル\]** ウィンドウ、**\[レジスタ\]** ウィンドウ、およびアドレス ブレークポイント\) を有効にします。  
  
 **ソースがない場合に逆アセンブリを表示する**  
 ソースを利用できないコードをデバッグしようとするときに、**\[逆アセンブル\]** ウィンドウが自動的に表示されます。  
  
 **ブレークポイントのフィルターを有効にする**  
 特定のプロセス、スレッド、またはコンピューターだけにフィルターが影響するように、ブレークポイントのフィルターの設定を有効にします。  
  
 **例外処理アシスタントを有効にする**  
 マネージ コード専用です。 マネージ例外は \[例外処理アシスタント\] ダイアログ ボックスを開きます。  「[Exception Assistant](../Topic/Exception%20Assistant.md)」を参照してください。  
  
 **ハンドルされていない例外で呼び出し履歴をアンワインドする**  
 **\[呼び出し履歴\]** ウィンドウで、未処理の例外が発生した前の時点に呼び出し履歴をロールバックします。  
  
 **マイ コードのみを有効にする**  
 デバッガーはユーザー コード \("マイ コード"\) だけを表示してステップ インします。システム コード、その他の最適化されたコード、デバッグ シンボルを持たないコードは無視されます。  
  
 **非ユーザー オブジェクトのすべてのメンバーを変数ウィンドウに表示する \(Visual Basic のみ\)**  
 非ユーザー コード \("マイ コード" 以外のコード\) に含まれるオブジェクトの非パブリック メンバーの表示をオンにします。  
  
 **起動時にユーザー コードが見つからないとき警告**  
 \[マイ コードのみ\] を有効にしてデバッグを開始したとき、ユーザー コード \("マイ コード"\) が存在しない場合に警告を行います。  
  
 **.NET Framework ソースのステッピングを有効にする**  
 デバッグ時に .NET Framework ソース コードにステップ インできます。 このオプションを有効にすると、\[マイ コードのみ\] が自動的に無効になります。.NET Framework シンボルは、キャッシュの場所へダウンロードされます。 キャッシュの場所は、**\[オプション\]** ダイアログ ボックス \(**\[デバッグ\]** カテゴリの **\[シンボル\]** ページ\) で変更できます。  
  
 **\[プロパティおよび演算子をステップ オーバーする \(マネージのみ\)\]**  
 デバッグ時にマネージ コード内のプロパティおよび演算子にステップ インしません。  
  
 **プロパティの評価とその他の暗黙的な関数の呼び出しを常に有効にする**  
 変数ウィンドウと **\[クイック ウォッチ\]** ダイアログ ボックスで、プロパティの自動評価と暗黙的な関数の呼び出しを有効にします。  
  
 **\[変数ウィンドウのオブジェクトに対して文字列変換関数を呼び出す \(C\# および JavaScript のみ\)\]**  
 変数ウィンドウでオブジェクトを評価するときに文字列変換呼び出しを暗黙的に実行します。 したがって、結果は型名ではなく、文字列として表示されます。 C\# コードのデバッグ時にのみ適用されます。 この設定は、DebuggerDisplay 属性によってオーバーライドされる場合があります \(「[DebuggerDisplay 属性を使用します](../debugger/using-the-debuggerdisplay-attribute.md)」をご覧ください\)。  
  
 **ソース サーバー サポートを有効にする**  
 SRCSRV \(`srcsrv.dll`\) プロトコルを実装するソース サーバーからソース ファイルを取得するように Visual Studio デバッガーに指示します。 このプロトコルを実装する 2 つのソース サーバーは Team Foundation Server と Debugging Tools for Windows です。 SrcSrv のセットアップの詳細については、Debugging Tools for Windows のドキュメントを参照してください。 さらに、「[シンボルとソース コードの管理](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)」をご覧ください。  
  
> [!IMPORTANT]
>  .pdb ファイルを読み取ることでそのファイル内の任意のコードを実行できるため、サーバーが信頼されていることを確認してください。  
  
 **ソース サーバー診断メッセージを出力ウィンドウに表示する**  
 ソース サーバーのサポートが有効な場合に、診断表示をオンにします。  
  
 **\[部分信頼アセンブリのソース サーバーを許可する \(マネージのみ\)\]**  
 ソース サーバーのサポートが有効になっているとき、この設定により、部分信頼アセンブリのソースを取得しないという既定の動作がオーバーライドされます。  
  
 **\[ブレークポイントおよび現在のステートメントのソース行全体を強調表示する\]**  
 デバッガーでブレークポイントまたは現在のステートメントを強調表示するときに、行全体を強調表示します。  
  
 **元のバージョンと完全に一致するソース ファイルを必要とする**  
 デバッグ中の実行可能ファイルをビルドしたときに使用したソース コードのバージョンが、ソース ファイルと一致するかどうかを検査するようにデバッガーに指示します。 バージョンが一致しない場合、一致するソースを検索するように指示するメッセージが表示されます。 一致するソースが見つからないときは、デバッグ時にソース コードが表示されません。  
  
 **\[出力ウィンドウの文字をすべてイミディエイト ウィンドウにリダイレクトする\]**  
 通常は**出力**ウィンドウに出力されるデバッガー メッセージをすべて**イミディエイト** ウィンドウに送信します。  
  
 **オブジェクトの生の構造体を変数ウィンドウに表示する**  
 すべてのオブジェクトの構造体ビューのカスタマイズをオフにします。 ビューのカスタマイズについて詳しくは、「[カスタム データ型の表示](../debugger/create-custom-views-of-dot-managed-objects.md)」をご覧ください。  
  
 **\[モジュールの読み込み中に JIT 最適化を抑制する \(マネージのみ\)\]**  
 デバッガーをアタッチするとき、モジュールの読み込み中 \(および JIT のコンパイル中\) にマネージ コードの JIT 最適化を無効にします。 最適化を無効にした場合、一部の問題のデバッグは簡単になりますが、パフォーマンスは低下します。 \[マイ コードのみ\] を使用しているときに JIT 最適化を抑制すると、非ユーザー コードがユーザー コード \("マイ コード"\) として表示される可能性があります。  
  
 **\[起動時にシンボルが見つからないとき警告 \(ネイティブのみ\)\]**  
 デバッガーにシンボル情報がないプログラムをデバッグすると、警告ダイアログ ボックスが表示されます。  
  
 **起動時、スクリプト デバッグが無効な場合は警告する**  
 デバッガーの起動時にスクリプト デバッグが無効である場合は、警告ダイアログ ボックスが表示されます。  
  
 **DLL エクスポートを読み込む**  
 DLL エクスポート テーブルを読み込みます。 DLL エクスポート テーブルのシンボル情報は、対応するシンボルのない Windows メッセージ、Windows プロシージャ \(WindowProc\)、COM オブジェクト、マーシャリング、DLL を操作する場合に役立ちます。 DLL エクスポート情報を読み取ると、オーバーヘッドがある程度発生します。 そのため、既定ではこの機能はオフになっています。  
  
 DLL のエクスポート テーブル内で使用できるシンボルを確認するには、`dumpbin /exports` を使います。 シンボルは、すべての 32 ビット システムの DLL に使うことができます。`dumpbin /exports` の出力を参照すると、英数字以外の文字を含む、正確な関数名を確認できます。 この情報は、関数にブレークポイントを設定するときに使用します。 DLL エクスポート テーブルの関数名は、デバッガーの他の場所で表示されるとき、切り捨てられることがあります。 関数は呼び出し順に表示され、現在の関数 \(入れ子の一番内側\) が先頭に表示されます。 詳細については、「[dumpbin \/exports](/visual-cpp/build/reference/dash-exports)」を参照してください。  
  
 **並列スタックの図を上下逆に表示**  
 スタックを **\[並列スタック\]** ウィンドウに表示する方向を制御します。  
  
 **\[書き込まれたデータで値が変更されなかった場合は GPU メモリ アクセス例外を無視する\]**  
 データが変更されなかった場合、デバッグ中に検出された競合状態を無視します。 詳細については、「[GPU コードのデバッグ](../debugger/debugging-gpu-code.md)」を参照してください。  
  
 **マネージ互換モードの使用**  
 既定のデバッグ エンジンをレガシ バージョンと置き換えて、次のシナリオを有効にします。  
  
-   独自の式エバリュエーターを提供する C\#、VB、または F\# 以外の .NET Framework 言語を使用しています \(これは C\+\+\/CLI を含みます\)。  
  
-   混合モード デバッグ時に、C\+\+ プロジェクトのエディット コンティニュを有効にします。  
  
 マネージ互換モードを選択すると、既定のデバッグ エンジンにのみ実装されている一部の機能は無効になります。  
  
 **ネイティブ互換モードの使用**  
 このオプションを選択すると、デバッガーは、新しいネイティブ デバッガーの代わりに Visual Studio 2010 のネイティブ デバッガーを使用します。  
  
 新しいデバッグ エンジンは .NET C\+\+ 式の評価をサポートしていないため、.NET C\+\+ コードをデバッグするときにはこのオプションを使用する必要があります。 ただし、ネイティブ互換モードを有効にすると、現在のデバッガーの実装に依存している多くの機能が無効になります。 たとえば、レガシ エンジンには、`std::string` などの Visual Studio 2015 プロジェクトの組み込み型のビジュアライザーの多くがありません。   このような場合、デバッグ機能を最適にご利用いただくためには、Visual Studio 2013 プロジェクトをお使いください。  
  
 **従来の C\# および VB の式エバリュエーターを使用する**  
 デバッガーは、Visual Studio 2015 の Roslyn ベースの式エバリュエーターの代わりに、Visual Studio 2013 の C\#\/VB の式エバリュエーターを使います。  
  
 **アンセーフ コードの可能性があるコードに対してカスタムのデバッガー ビジュアライザーを使う際に警告する**  
 Visual Studio は、デバッグ対象プロセスでコードを実行中のカスタム デバッガー ビジュアライザーを使っているときに、アンセーフ コードを実行している可能性がある場合、警告します。  
  
 **Windows デバッグ ヒープ アロケーター を有効にする \(ネイティブのみ\)**  
 ヒープ診断を向上させるために Windows デバッグ ヒープを有効にします。 このオプションを有効にすると、デバッグ パフォーマンスに影響を与えます。  
  
 **XAML の UI デバッグ ツールを有効にします**  
 サポートされるプロジェクト タイプのデバッグを開始すると \(F5\)、ライブ ビジュアル ツリーとライブ プロパティ エクスプローラーのウィンドウが表示されます。 詳細については、「[デバッグ中に XAML のプロパティを調べます。](../debugger/inspect-xaml-properties-while-debugging.md)」を参照してください。  
  
 **Live Visual Tree で選択された要素をプレビューする**  
 コンテキストが選択されている XAML 要素は、ライブ ビジュアル ツリー ウィンドウでも選択されています。  
  
 **デバッグ中に診断ツールを有効にします**  
 デバッグ中に \[診断ツール\] ウィンドウが表示されます。 詳細については、「[デバッガーに統合された診断](../Topic/Debugger-integrated%20profiling.md)」を参照してください。  
  
 **デバッグ中に経過時間の PerfTip を表示する**  
 デバッグ中に、特定のメソッド呼び出しの経過時間がコード ウィンドウに表示されます。  
  
 **エディット コンティニュを有効にする**  
 デバッグ中にエディット コンティニュ機能を使用できます。  
  
 **ネイティブのエディット コンティニュを有効にする**  
 ネイティブ C\+\+ コードのデバッグ中にエディット コンティニュ機能を使用できます。 詳細については、「[エディット コンティニュ \(Visual C\+\+\)](../debugger/edit-and-continue-visual-cpp.md)」を参照してください。  
  
 **コンティニュに変更を適用する \(ネイティブのみ\)**  
 Visual Studio は、ブレーク状態からプロセスを続行するとき、未処理のコード変更を自動的にコンパイルして適用します。 選択されていない場合は、\[デバッグ\] メニューの下にある \[コード変更を適用\] の項目を使って変更を適用することができます。  
  
 **古いコードの警告を表示する \(ネイティブのみ\)**  
 古いコードに関する警告を取得します。  
  
 **プリコンパイルを許可する \(ネイティブのみ\)**  
 プリコンパイルが許可されます。  
  
## 参照  
 [Visual Studio でのデバッグ](../debugger/debugging-in-visual-studio.md)