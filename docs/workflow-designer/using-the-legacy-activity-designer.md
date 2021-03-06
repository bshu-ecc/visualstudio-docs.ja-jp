---
title: "従来のアクティビティ デザイナーを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- activities, configuring
- custom activities
- Activity Designer
- child activities, adding
- activities, adding child
- activities, creating custom
ms.assetid: 2fea8a05-6e58-423d-94bf-a822b15ffb80
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 65510d727fdf0640ca8efa646a14d0814951cd4b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="using-the-legacy-activity-designer"></a>従来のアクティビティ デザイナーの使用
このトピックでは、従来の [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]でアクティビティ デザイナーを使用する方法について説明します。 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] または [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] を対象とする場合は、従来のデザイナーを使用します。  
  
 アクティビティ デザイナーを使用すると、独自のカスタム アクティビティを作成できます。  
  
## <a name="creating-a-custom-activity"></a>カスタム アクティビティの作成  
 アクティビティ デザイナを使ってカスタム アクティビティを作成するには、次の手順に従います。  
  
1.  **プロジェクト** メニューのをクリックして**追加アクティビティ**です。  
  
2.  選択、**アクティビティ**または**アクティビティ (コード分離付き)**テンプレート。  
  
    1.  使用して、**アクティビティ**アクティビティ定義と同じコード ファイル内のユーザー コード アクティビティを作成するテンプレートです。  
  
    2.  使用して、**アクティビティ (コード分離付き)**アクティビティ定義がワークフロー マークアップと個別のコード ファイル内のユーザー コードで表されるアクティビティを作成するテンプレートです。  
  
3.  アクティビティ名を入力または既定の名前を保持し、クリックして**追加**です。  
  
 型の新しいプロジェクトを作成することで、カスタム アクティビティのセットを作成することも**Workflow Activity Library**です。 このプロジェクトの種類の詳細については、次を参照してください。[する方法: ワークフロー アクティビティ ライブラリ (レガシ) を作成](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md)です。  
  
## <a name="configuring-an-activity"></a>アクティビティの構成  
 アクティビティ デザイナがアクティブであるときに、プロパティ ブラウザを使用すると、次の表にリストされているプロパティを構成できます。  
  
|プロパティ|コメント|  
|--------------|--------------|  
|**名前**|アクティビティの名前。|  
|**基本クラス**|アクティビティの派生元の基本クラス。 既定の基本クラスは[SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020)です。 **プロパティ**ウィンドウで、をクリックして、**ベース クラス**省略記号**[...]**で別の基本クラスを選択、[を参照して .NET の種類 ダイアログ ボックス (レガシ) を選択](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md)です。|  
|**説明**|アクティビティに関するユーザー定義の説明。|  
|**有効**|設定**True**既定では、アクティビティの実行と検証を有効にします。 設定**False**アクティビティの実行と検証を無効にします。 アクティビティの実行と検証については、次を参照してください。[ワークフロー アクティビティの開発](http://go.microsoft.com/fwlink?LinkID=65024)です。|  
  
## <a name="adding-child-activities"></a>子アクティビティの追加  
 子アクティビティを、ツールボックスから設計中のアクティビティまでドラッグすることができます。 その後、プロパティ ブラウザを使ってそれぞれの子アクティビティを構成できます。  
  
## <a name="see-also"></a>関連項目  
 [ワークフロー活動の開発](http://go.microsoft.com/fwlink?LinkID=65024)   
 [カスタム アクティビティを作成します。](http://go.microsoft.com/fwlink?LinkID=65021)   
 [従来のワークフロー アクティビティ](../workflow-designer/legacy-workflow-activities.md)   
 [カスタム アクティビティのサンプル](http://go.microsoft.com/fwlink?LinkID=65022)   
 [方法: ワークフロー アクティビティ ライブラリ (レガシ) を作成します。](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md)   
 [従来のワークフロー デザイナーの使用](../workflow-designer/using-the-legacy-workflow-designer.md)