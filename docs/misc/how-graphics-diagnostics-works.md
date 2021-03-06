---
title: "グラフィックス診断のしくみ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ae14497-c77c-4399-bc0c-595caba23656
caps.latest.revision: 2
caps.handback.revision: 2
ms.author: "mithom"
manager: "douge"
---
# グラフィックス診断のしくみ
ここにイントロダクションを挿入します。  
  
## グラフィックス診断のしくみ  
 グラフィックス診断を使用するには、まず、実行中のアプリが Direct3D API を使用する方法に関する情報を記録し、次に、記録された動作を後で調べます。  指定したフレームについて記録される情報には、画面のクリア、ジオメトリの描画、計算シェーダーのディスパッチ、またはグラフィックス デバイスの状態の変更などを行う API 呼び出しとその引数、および間接的に参照されるバッファーとオブジェクトのコピーが含まれます。  また、フレームがレンダリングされる前に、セットアップと初期化に関連する API 呼び出しが記録されます。  記録される情報は、*グラフィックス ログ* \(.vsglog\) ファイルに書き込まれます。  
  
 開発用コンピューター、リモート コンピューター、またはリモート デバイスでグラフィックス イベントを再生することにより、グラフィックス ログに記録されたレンダリング動作を再作成できます。  再生コンピューターは、グラフィックス ログが最初にキャプチャされたコンピューターまたはデバイスと同じか、別のコンピューターまたはデバイスにすることができます。  ほとんどの再生機能に関して、再生コンピューターのグラフィックス ハードウェアを使用してグラフィックス イベントが再生されますが、HLSL デバッガーが使用される場合は、CPU でエミュレートされた GPU を使用することによりシェーダー コードが常に再生されます。  エミュレートされた GPU を使用すると、再生コンピューターのグラフィックス ハードウェアがハードウェア デバッグをサポートするかどうかに関係なく、シェーダー コードのステップ実行や変数の調査を行ったり、その他の一般的なデバッグ機能を使用したりできます。  
  
> [!NOTE]
>  グラフィックス ログには関連情報の大部分が内部的にキャプチャされますが、グラフィック診断の一部の機能を十分に活用するには追加の情報が必要です。  たとえば、グラフィックの呼び出し履歴の機能を十分に活用するには、プログラム データベース \(.pdb\) ファイルとアプリケーションのソース コードが必要です。  HLSL シェーダーのソース コードをデバッグするには、シェーダーのソース コードも必要です   \(シェーダーが D3D11.1 シェーダー コンパイラを使用してコンパイルされていて、デバッグ情報を使用できる場合は、キャプチャ中にシェーダーのソース コードがグラフィックス ログに埋め込まれます\)。  
  
> [!NOTE]
>  Windows または DirectX の以前のバージョンでは特定の API を使用できない可能性があるため、これらの API 呼び出しをキャプチャしたグラフィックス ログは、サポートしていない再生コンピューター上では再生できません。  
  
### グラフィックス ログ  
 グラフィックス ログには、実行中の DirectX のグラフィックス アプリケーションからキャプチャされた 1 つ以上のフレームが含まれます。  グラフィックス ログは単体で使用できるため、これらのフレームは外部情報または参照なしに後で再作成できます。  つまり、グラフィックス ログを他の開発者と共有したり、別のコンピューターで問題を調べたりできます。また、モデルとテクスチャが開発で変更されていても、変更前のグラフィックス ログを調べることができます。  データとレンダリングの結果を比較するために、複数のグラフィックス ログ \(.vsglog\) ファイルを同時に読み込むこともできます。  
  
##### グラフィックス ログ \(vsglog\) ファイルを開くには  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] のメニュー バーで、**\[ファイル\]**、**\[開く\]**、**\[ファイル\]** の順に選択します。  **\[ファイルを開く\]** ダイアログ ボックスが表示されます。  
  
2.  開くグラフィックス ログ \(.vsglog\) ファイルを指定し、**\[開く\]** ボタンをクリックします。  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] の一部であるグラフィック ツールを使用して、グラフィックス ログからメッシュおよびテクスチャのコピーを展開、変更および保存できます。  ただし、グラフィックス ログの内容はこの変更の影響を受けません。  これらのグラフィック ツールについては、「[ゲームとアプリケーション用の 3D アセットの操作](../designers/working-with-3-d-assets-for-games-and-apps.md)」を参照してください。