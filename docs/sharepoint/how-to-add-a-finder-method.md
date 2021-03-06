---
title: "方法: Finder メソッドを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], get entities
- Business Data Connectivity service [SharePoint development in Visual Studio], return entities
- BDC [SharePoint development in Visual Studio], return entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Finder method
- Business Data Connectivity service [SharePoint development in Visual Studio], get entities
- BDC [SharePoint development in Visual Studio], Finder method
ms.assetid: 5de2cae3-d1f7-4a68-aac0-458967aca692
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f0aa8888456d75554b2270058b844c7f76cb63fb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-finder-method"></a>方法: Finder メソッドを追加する
  Web パーツまたはリスト内のエンティティの一覧を表示するビジネス データ接続サービスを有効にする必要がありますを作成する、 *Finder*メソッドです。 Finder メソッドは、エンティティのインスタンスのコレクションを返す特殊な方法です。 詳細については、次を参照してください。[ビジネス データ接続モデルをデザイン](../sharepoint/designing-a-business-data-connectivity-model.md)です。  
  
### <a name="to-create-a-finder-method"></a>Finder メソッドを作成するには  
  
1.  BDC デザイナーでは、エンティティを選択します。  
  
     詳細については、次を参照してください。[する方法: エンティティをモデルに追加](../sharepoint/how-to-add-an-entity-to-a-model.md)です。  
  
2.  メニュー バーで、次のように選択します。**ビュー**、**その他のウィンドウ**、 **BDC メソッドの詳細**です。  
  
     **BDC メソッドの詳細**ウィンドウが開きます。 詳細については、 **BDC メソッドの詳細**ウィンドウを参照してください[BDC モデルのデザイン ツールの概要](../sharepoint/bdc-model-design-tools-overview.md)です。  
  
3.  **メソッドを追加**一覧で、選択**Finder メソッドの作成**です。  
  
     Visual Studio では、メソッド、戻りパラメーター、および型記述子を追加します。  
  
4.  エンティティ コレクション型記述子として、型記述子を構成します。 エンティティ コレクション型記述子を作成する方法の詳細については、次を参照してください。[する方法: パラメーターの型記述子を定義する](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)です。  
  
    > [!NOTE]  
    >  Specific Finder メソッドは、エンティティに追加した場合、この手順を実行する必要はありません。 Visual Studio では、Specific Finder メソッドで定義されている型記述子を使用します。  
  
5.  **ソリューション エクスプ ローラー**エンティティには、生成されたサービス コード ファイルのショートカット メニューを開きを選択し、**コードの表示**です。 サービス コード ファイルの詳細については、次を参照してください。[ビジネス データ接続モデルを作成する](../sharepoint/creating-a-business-data-connectivity-model.md)です。  
  
6.  Finder メソッドにコードを追加します。 このコードは次のタスクを実行します。  
  
    -   データ ソースからデータを取得します。  
  
    -   BDC サービスにエンティティの一覧を返します。  
  
     次の例は、のコレクションを返します`Contact`SQL Server の AdventureWorks サンプル データベースからデータを使用してエンティティです。  
  
    > [!NOTE]  
    >  値を置き換える、`ServerName`フィールドに、サーバーの名前。  
  
     [!code-csharp[SP_BDC#2](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#2)]  
  
## <a name="see-also"></a>関連項目  
 [BDC モデルのデザイン ツールの概要](../sharepoint/bdc-model-design-tools-overview.md)   
 [ビジネス データ接続モデルの設計](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [方法: Specificfinder メソッドを追加します。](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [方法: Creator メソッドを追加](../sharepoint/how-to-add-a-creator-method.md)   
 [方法: Deleter メソッドを追加](../sharepoint/how-to-add-a-deleter-method.md)   
 [方法: Updater メソッドを追加](../sharepoint/how-to-add-an-updater-method.md)   
 [方法: メソッドにパラメーターを追加](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [方法: メソッド インスタンスを定義する](../sharepoint/how-to-define-a-method-instance.md)  
  
  