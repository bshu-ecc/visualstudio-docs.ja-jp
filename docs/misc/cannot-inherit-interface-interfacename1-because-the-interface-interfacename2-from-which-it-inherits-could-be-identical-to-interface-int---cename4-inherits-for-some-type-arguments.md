---
title: "継承元のインターフェイス &#39;&lt;interfacename2&gt;&#39; が、インターフェイス &#39;&lt;interfacename4&gt;&#39; の継承元であるインターフェイス &#39;&lt;interfacename3&gt;&#39; と、いくつかの型引数において同一である可能性があるため、インターフェイス &#39;&lt;interfacename1&gt;&#39; を継承できません。 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32122"
  - "bc32122"
helpviewer_keywords: 
  - "BC32122"
ms.assetid: 64a66ec7-0f5f-4804-a92b-9a6279fdfd6d
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 継承元のインターフェイス &#39;&lt;interfacename2&gt;&#39; が、インターフェイス &#39;&lt;interfacename4&gt;&#39; の継承元であるインターフェイス &#39;&lt;interfacename3&gt;&#39; と、いくつかの型引数において同一である可能性があるため、インターフェイス &#39;&lt;interfacename1&gt;&#39; を継承できません。
ジェネリック インターフェイスが 2 つ以上のジェネリック インターフェイスから継承されており、その継承のうちの 2 つが、型引数の特定の値について競合している可能性があります。  
  
 次のステートメントでは、このエラーが生成される可能性があります。  
  
```  
Public Interface interfaceA(Of u) End Interface Public Interface interfaceX(Of v) Inherits interfaceA(Of v) End Interface Public Interface interfaceY(Of w) Inherits interfaceA(Of w) End Interface Public Interface derivedInterface(Of t1, t2) Inherits interfaceX(Of t1), interfaceY(Of t2) End Interface  
```  
  
 `derivedInterface` が `t1` と `t2` の両方に同じ型を指定して構築または実装されている場合、同一の型引数を含む 2 つのバージョンの `interfaceA` を継承する必要があります。 この場合、どのバージョンにアクセスするかがあいまいになります。  
  
 **エラー ID:** BC32122  
  
### このエラーを解決するには  
  
-   競合しないように、派生インターフェイスに指定された型引数のいずれかを変更します。  
  
     または  
  
-   `Inherits` ステートメントから、潜在的な継承または実装の競合を引き起こすいずれかのインターフェイスを削除します。  
  
## 参照  
 [ビルド内にありません: インターフェイスの概要](http://msdn.microsoft.com/ja-jp/f96bb470-c1b8-4c73-89bc-6f536b798da1)   
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [Visual Basic におけるジェネリック型](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)