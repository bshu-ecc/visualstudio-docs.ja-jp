---
title: "色、線のスタイル、およびその他の図形のプロパティを制御する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c06d0066-24aa-4c65-b91c-c2089b81ec8d
caps.latest.revision: "2"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 1d2ed7170189ad48474a7cf8422386b6198ccc9c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>色、線のスタイル、およびその他のシェイプのプロパティの管理
一部の図形のプロパティ色 '公開できる' - などは、リンクされている図形のドメイン プロパティにします。 他のユーザーは、直接制御する必要があります。  
  
## <a name="exposing-a-property"></a>プロパティを公開します。  
 いくつかの色などの図形のプロパティは、ドメイン プロパティの値にリンクすることができます。  
  
 DSL 定義では、図形、コネクタまたはダイアグラムのクラスを選択します。 そのコンテキスト メニューで、次のように選択します。**公開追加**、塗りつぶしの色など、目的のプロパティを選択します。  
  
 図形には、今すぐプログラム コードやユーザーとして設定できるドメイン プロパティがあります。  
  
## <a name="dynamically-updating-an-exposed-property"></a>公開されたプロパティを動的に更新  
 通常、公開されているプロパティを別のプロパティに依存するようにします。 たとえば、ことができますが赤色に特定のドメインのプロパティは使用されるたびにするための図形が 0 未満です。 この依存関係を作成、[ルール](../modeling/rules-propagate-changes-within-the-model.md)です。 例:  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
namespace ExampleNamespace  
{  
 // Attribute associates the rule with class:  
 [RuleOn(typeof(CarShape), FireTime = TimeToFire.TopLevelCommit)]  
 // The rule is a class derived from one of the abstract rules:  
 class CarShapeAddRule : AddRule  
 {  
 // Override the abstract method:  
 public override void ElementAdded(ElementAddedEventArgs e)  
 {  
 base.ElementAdded(e);  
 CarShape shape = e.ModelElement as CarShape;  
 Store store = shape.Store;  
 // Ignore this call if we're currently loading a model:  
 if (store.TransactionManager.CurrentTransaction.IsSerializing)   
  return;  
 Car car = shape.ModelElement as Car;  
 // Code here propagates change as required - for example:  
 shape.FillColor = car.Somebool ? System.Drawing.Color.Red : System.Drawing.Color.Green;   
 }  
}  
 // The rule must be registered:  
 public partial class ExampleDomainModel  
 {  
 protected override Type[] GetCustomDomainModelTypes()  
 {  
  List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
  types.Add(typeof(CarShapeAddRule));  
  // If you add more rules, list them here.   
  return types.ToArray();  
 }  
 }  
}  
```