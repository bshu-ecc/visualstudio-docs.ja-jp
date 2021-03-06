---
title: "方法: エンティティをモデルに追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EntityTool
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], entity
- Business Data Connectivity service [SharePoint development in Visual Studio], adding an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], entity
- BDC [SharePoint development in Visual Studio], adding an entity
ms.assetid: 139a6639-dabe-4e14-bb64-e5f4efb6f2fb
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d8cc1bf4871ef91c5b08cb77963a70e422ee3cdc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-an-entity-to-a-model"></a>方法: モデルにエンティティを追加する
  エンティティを作成するには、Visual Studio からエンティティ コントロールを追加**ツールボックス**ビジネス データ接続 (BDC) をデザイナーにします。  
  
### <a name="to-add-an-entity-to-the-model"></a>モデルにエンティティを追加するには  
  
1.  BDC プロジェクトを作成するか、既存の BDC プロジェクトを開きます。 詳細については、次を参照してください。[ビジネス データ接続モデルを作成する](../sharepoint/creating-a-business-data-connectivity-model.md)です。  
  
2.  **ツールボックス**から、 **BusinessDataCatalog**グループで、追加、**エンティティ**コントロールをデザイナーにします。  
  
     デザイナーに新しいエンティティが表示されます。 Visual Studio は追加、`<Entity>`要素を BDC モデル ファイル、プロジェクト内の XML にします。 エンティティ要素の属性に関する詳細については、次を参照してください。[エンティティ](http://go.microsoft.com/fwlink/?LinkId=169296)です。  
  
3.  デザイナーで、エンティティのショートカット メニューを開き、選択**追加**を選択し**識別子**です。  
  
     エンティティに新しい識別子が表示されます。  
  
    > [!NOTE]  
    >  エンティティとの識別子の名前を変更することができます、**プロパティ**ウィンドウです。  
  
4.  クラスでは、エンティティのフィールドを定義します。 プロジェクトに新しいクラスを追加するか、オブジェクト リレーショナル デザイナー (O/R デザイナー) などの他のツールを使用して作成された既存のクラスを使用します。 次の例では、連絡先を名前付きエンティティ クラスを示します。  
  
     [!code-csharp[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/CSharp/sp_bdc_entity_data_class/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/VisualBasic/sp_bdc_entity_data_class/bdcmodel1/contact.vb#1)]  
  
## <a name="see-also"></a>関連項目  
 [方法: Creator メソッドを追加](../sharepoint/how-to-add-a-creator-method.md)   
 [方法: Deleter メソッドを追加](../sharepoint/how-to-add-a-deleter-method.md)   
 [方法: Updater メソッドを追加](../sharepoint/how-to-add-an-updater-method.md)   
 [方法: Finder メソッドを追加](../sharepoint/how-to-add-a-finder-method.md)   
 [方法: SpecificFinder メソッドを追加する](../sharepoint/how-to-add-a-specific-finder-method.md)  
  
  