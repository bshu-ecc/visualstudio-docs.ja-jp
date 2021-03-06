---
title: "依存関係図を拡張する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
ms.assetid: 83fca301-b008-485a-87eb-218050e71451
caps.latest.revision: "39"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 2b661d894a471a3734a54806a89381d06fd3bd2d
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="extend-dependency-diagrams"></a>依存関係図を拡張します。
作成し、依存関係の図を更新し、Visual Studio での依存関係図と照らし合わせてプログラム コードの構造を検証するコードを記述することができます。 図のショートカット (コンテキスト) メニューに表示するコマンドを追加し、ドラッグ アンド ドロップ ジェスチャをカスタマイズし、テキスト テンプレートからレイヤー モデルにアクセスすることができます。 これらの拡張機能を VSIX (Visual Studio Integration Extension) にパッケージ化し、他の Visual Studio ユーザーに配布することができます。  
  
 依存関係図についての詳細についてを参照してください。  
  
-   [依存関係図: リファレンス](../modeling/layer-diagrams-reference.md)  
  
-   [依存関係図: ガイドライン](../modeling/layer-diagrams-guidelines.md)  
  
-   [コードからの依存関係図の作成](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [依存関係図を使用したコードの検証](../modeling/validate-code-with-layer-diagrams.md)  
  
##  <a name="prereqs"></a> 必要条件  
 レイヤー拡張機能を開発するコンピューターに以下の項目がインストールされている必要があります。  
  
-   Visual Studio  
  
-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)  
  
-   Visual Studio のモデリング SDK  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
 適切なバージョンの Visual Studio をレイヤー拡張機能を実行するコンピューターにインストールしておく必要があります。 詳細については、次を参照してください。[レイヤー モデル拡張機能の配置](../modeling/deploy-a-layer-model-extension.md)です。  
  
 Visual Studio のバージョンをサポートして、依存関係図を参照してください[アーキテクチャおよびモデリング ツールのバージョン サポート](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [依存関係図にコマンドおよびジェスチャを追加する](../modeling/add-commands-and-gestures-to-layer-diagrams.md)  
  
 [カスタム アーキテクチャ検証を依存関係図に追加する](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)  
  
 [依存関係図へのカスタム プロパティの追加](../modeling/add-custom-properties-to-layer-diagrams.md)  
  
 [プログラム コードでレイヤー モデル内を移動し、レイヤー モデルを更新する](../modeling/navigate-and-update-layer-models-in-program-code.md)  
  
 [レイヤー モデル拡張機能の配置](../modeling/deploy-a-layer-model-extension.md)  
  
 [依存関係図の拡張機能のトラブルシューティング](../modeling/troubleshoot-extensions-for-layer-diagrams.md)  
  
## <a name="see-also"></a>関連項目  
 [依存関係図: リファレンス](../modeling/layer-diagrams-reference.md)   
 [依存関係図: ガイドライン](../modeling/layer-diagrams-guidelines.md)   
 [コードから依存関係のダイアグラムを作成します。](../modeling/create-layer-diagrams-from-your-code.md)   
 [依存関係図を使用したコードの検証](../modeling/validate-code-with-layer-diagrams.md)   
