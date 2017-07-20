---
title: "チャネルの管理 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.tools.managechannels"
helpviewer_keywords: 
  - "同時実行ビジュアライザー、チャネルの管理"
ms.assetid: 507b06e9-bb56-4a72-8fd5-f91f958da6fc
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# チャネルの管理
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

同時実行ビジュアライザーを **\[スレッド ビュー\]** で、特定のパターンを確認できるように、プロセスのチャネルを編成できます。  チャネルを並べ替え、上下に移動したり、非表示にしたり、表示したりすることができます。  
  
## \[並べ替え\]  
 コントロールで現在のズーム レベルに基づいて、異なる基準でスレッドを並べ替えるには、並べ替えを使用できます。  これにより、特定のパターンを検索する場合に特に便利です。  これらの条件によって並べ替えることができますが、T:  
  
|\[抽出条件\]|定義|  
|--------------|--------|  
|開始時間|開始時間で並べ替えます。スレッド。  これは、既定の並べ替え順序です。|  
|終了時刻|終了時間で並べ替えます。スレッド。|  
|実行|実行に費やされた時間の割合で、スレッドを並べ替えます。|  
|同期|同期に費やされた時間の割合で、スレッドを並べ替えます。|  
|入出力|I\/O に費やされた時間の割合で、スレッドを並べ替えます \(データの読み取りと書き込み\)。|  
|Sleep|スリープに費やされた時間の割合で、スレッドを並べ替えます。|  
|ページング|ページングに費やされた時間の割合で、スレッドを並べ替えます。|  
|優先|優先に費やされた時間の割合で、スレッドを並べ替えます。|  
|UI 処理|ユーザー インターフェイスの処理に費やされた時間の割合で、スレッドを並べ替えます。|  
  
## 指定チャネルを上下に移動します。  
 リストのチャネルを上下に移動するためにこれらのコントロールを使用できます。  たとえば、特定のパターンまたはスレッド間の関係を調べるのに役立つ関連チャネルをを塗りつぶすことができます。  
  
## Top または Bottom を付けるよう指定チャネルを移動します。  
 それをチェックするときに特定のパターンを調査したり、移動します。一番チャネルをできますが、リストの先頭または末尾に指定チャネルを移動します。  
  
## 非表示指定チャネル  
 チャネルを非表示にする場合は、このコントロールをクリックします。  たとえば、スレッドがマネージ プロセスの有効期間中、100 同期、他のスレッドを分析する際に非表示にできます。  
  
> [!NOTE]
>  スレッドを非表示にすると、アクティブな凡例とプロファイル レポートに示される計算時間から削除します。  
  
## すべてのチャネルを表示  
 このコントロールは、一つ以上のチャネルが非表示のときにアクティブになります。  これを選択すると、すべての表示要素は時間の計算に表示され、その値が返されます。  
  
## マーカーを先頭へ移動  
 トレースがマーカー イベントが含まれている場合は、タイムラインの上にマーカー チャネルを移動する場合は、このコマンドを使用できます。  相対順序は維持されます。  
  
## スレッドによってグループ マーカー  
 トレースがマーカー イベントが含まれている場合、マーカー イベントを生成したスレッドでマーカー チャネルをグループ化する場合は、このコマンドを使用できます。ディスク チャネルは、チャネルのリストの先頭に置かれ、GPU チャネルで下に移動します。  
  
## 参照  
 [ズーム コントロール \(スレッド ビュー\)](../profiling/zoom-control-threads-view.md)   
 [測定モード オン\/オフ](../profiling/measure-mode-on-off.md)   
 [スレッド ビュー](../profiling/threads-view-parallel-performance.md)