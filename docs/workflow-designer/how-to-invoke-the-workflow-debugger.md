---
title: "方法: ワークフロー デバッガーを起動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34c592af-f4f6-4d02-99f6-63a94698e48b
caps.latest.revision: "9"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d7fbdb1851669d704cb8a44f8144291c04ae0ce
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-invoke-the-workflow-debugger"></a>ワークフロー デバッガーを呼び出す方法
ほとんどの場合、他の Visual Studio プログラミング言語で書かれたプログラムをデバッグするときと同じようにして、ワークフローをデバッグすることができます。 ワークフロー デバッガーは、次の方法で開始できます。  
  
-   選択**プロセスにアタッチする**上、**デバッグ** メニューのワークフロー インスタンスの実行中のホスト プロセスを選択します。 この手順は、マネージ コードのホスト プロセスへのアタッチと同じです。  
  
-   キーを押して**f5 キーを押して**ワークフローのインスタンスを実行を開始するか、ブレークポイントにヒットした後も引き続き実行します。  
  
-   リモート デバッグを使用します。 リモート デバッグの使用方法の詳細については、次を参照してください。[する方法: リモート デバッグを有効にする](http://go.microsoft.com/fwlink/?LinkId=196257)です。  
  
    > [!NOTE]
    >  ワークフロー アプリケーションが x86 を対象とする場合のアーキテクチャが、64 ビットのオペレーティング システムを実行しているコンピューターでホストされているリモート デバッグが機能しませんしない限り、および[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]にインストールされているリモート コンピューターまたはターゲットにワークフロー アプリケーションを変更**任意の CPU**です。  
  
### <a name="stepping-through-code"></a>コードのステップ実行  
  
-   **ステップ イン**: を使用して、アクティビティにステップ インできます**F11**です。 デバッガーは、任意の定義済みハンドラーにステップ インします。 ハンドラーが定義されていない場合は、アクティビティをステップ オーバーするか、(他のアクティビティを含む) 複合アクティビティの場合には、実行される最初のアクティビティにステップ インします。  
  
-   **ステップ アウト:**からステップ アウトを使用して、アクティビティできます**Shift F11**です。 アクティビティからステップ アウトすると、現在のアクティビティとすべての兄弟アクティビティは最後まで実行されます。 その後、デバッガーは現在のアクティビティの親で停止します。 コード ハンドラーからステップ アウトするとき、デバッガーはハンドラーに関連付けられたアクティビティで停止します。  
  
-   **ステップ オーバー**: できますをステップ オーバーするアクティビティを使用して、 **F10**です。 複合アクティビティをステップ オーバーするときは、デバッガーが、複合アクティビティの最初の実行可能な子で停止します。 複合ではないアクティビティ (<xref:System.Activities.Statements.Assign> アクティビティなど) をステップ オーバーするときは、デバッガーが、そのアクティビティおよび関連するハンドラーを実行して、次のアクティビティで停止します。 実行されるアクティビティが複合アクティビティの最後の子アクティビティである場合、デバッガーは、それを実行した後に親アクティビティで停止します。  
  
### <a name="debugging-with-f5"></a>F5 キーを使ったデバッグ  
  
-   ワークフロー コンソール アプリケーション プロジェクトを作成している場合が単にキーを押して**f5 キーを押して**に、アプリケーションとワークフローのデバッグを開始します。 アクティビティ ライブラリを単独で構築する場合は、実行可能なホスト アプリケーションをスタートアップ プロジェクトとして用意する必要があります。 スタートアップ プロジェクトを設定する**ソリューション エクスプ ローラー**をホストのプロジェクト名を右クリックし、**スタートアップ プロジェクトとして設定**です。  
  
## <a name="see-also"></a>関連項目  
 [方法: ワークフロー内のブレークポイントを設定](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [ワークフロー デザイナーを使用したワークフローのデバッグ](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)