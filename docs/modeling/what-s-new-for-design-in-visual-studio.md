---
title: "どのような &#39; s の新しい Visual Studio での設計の |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
ms.assetid: 36ab5c17-6dc0-4075-a28e-a0fa49b11260
caps.latest.revision: "32"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: ce1172baf41cf670b253b2420f5538607addfeb7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="what39s-new-for-design-in-visual-studio"></a>どのような &#39; s の新しい Visual Studio でデザイン

## <a name="live-dependency-validation"></a>ライブの依存関係の検証

技術的負債を管理するための重要な部分は、不要な依存関係を削除します。
依存関係のライブ検証が入っているの問題に関する正確な情報を提供して、エラーの一覧と、エディターの新機能の完全な効果します。

![アクションでライブの依存関係の検証](media/dep-validation-whatsnew-01.png)

やすくしやすいですが、変更、関連した用語を「レイヤー図」を「依存関係ダイアグラム」に依存関係の検証を行うには、オーサリング エクスペリエンスが変更されました。

**アーキテクチャ**メニューが直接依存関係ダイアグラムを作成するコマンドを含むようになりました。

![[アーキテクチャ] メニュー上のライブの依存関係アイテム](media/dep-validation-whatsnew-02.png)

... わかりやすいように、依存関係のダイアグラムでは、およびその説明、レイヤーのプロパティの名前が変更されているとします。

![ライブの依存関係プロパティの名前を更新します。](media/dep-validation-whatsnew-03.png)

表示、ソリューションの現在のコードの分析結果にすぐに、変更の影響、ダイアグラムを保存するたびにします。 できなくなります「依存関係の検証」コマンドの完了を待機する必要はありません。

詳細については、次を参照してください。[このブログの投稿](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/)です。 
 
## <a name="uml-designers-have-been-removed"></a>UML デザイナーが削除されました

UML デザイナーは、このバージョンの Visual Studio Enterprise から削除されています。

* UML 図が XML ファイルとして表示されるようになりました
* UML モデル エクスプ ローラーは存在しません
* モデリング プロジェクトの依存関係の検証の参照は使用されなく
* ソリューション エクスプ ローラーで、「レイヤー参照」ノードが表示されなくなります
* 依存関係 (層) ダイアグラムで「検証」ビルド アクションは使用されなく - ビルド タスクが削除されました 
* バージョン間のラウンド トリップを保持する、プロジェクトの構造
* ことができますも開いて、作成、編集、および依存関係 (層) 図を XML として保存
* 依存関係 (Layer) の図にリンクされている TFS の作業項目は、デザイン画面にアクセスできません。
* DSL またはレイヤーから戻るリンクはサポートされていません 
* Modeling SDK の UML 拡張機能は現在サポートされていません

ただし、.NET および C++ コードのアーキテクチャの視覚化はから利用できるサポート[コード マップの](map-dependencies-across-your-solutions.md)、および上で説明した依存関係の検証を大幅に向上します。

UML デザイナーの重要なユーザーの場合は、UML のニーズに代替のツールを決定するときに、Visual Studio 2015 またはそれ以前のバージョンを使用する続行することができます。

詳細については、次を参照してください。[このブログの投稿](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/)です。 

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

<a name="VersionSupport"></a>
##  <a name="version-support-for-architecture-and-modeling-tools"></a>アーキテクチャ ツールとモデリング ツールのバージョン サポート  

Visual Studio には、使用できるバージョンがいくつかあります。 そのうちの一部においては、アーキテクチャ ツールとモデリング ツールのサポートが提供されていません。 各ツールの利用可能情報を次の表に示します。  
  
|**機能**|**Enterprise**|**Professional**|**Community**|**Express**|  
|-----------------|--------------------|----------------------|-------------------|-----------------|  
|**コード マップ**|はい|注 (1) を参照してください。|-|-|  
|**依存関係図**|はい|注 (2) を参照してください。|注 (2) を参照してください。|-|  
|**グラフを向け**(DGML ダイアグラム)|はい|はい|はい|-|  
|**コード クローン**|はい|-|-|-|  
  
注 (1): コード マップの読み取り、コード マップのフィルター処理、新しいジェネリック ノードの追加、選択範囲からの新しい有向グラフの作成のみをサポートします。

注 (2): のみサポートされて、依存関係図を読み取るします。
