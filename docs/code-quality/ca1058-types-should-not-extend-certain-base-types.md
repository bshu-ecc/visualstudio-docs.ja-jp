---
title: "CA1058: 型は特定の基本型を拡張しない |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 45cddd908c53d129a230b998c6dad03196a31c49
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: 型は、一定の基本型を拡張することはできません
|||  
|-|-|  
|TypeName|TypesShouldNotExtendCertainBaseTypes|  
|CheckId|CA1058|  
|カテゴリ|Microsoft.Design|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 外部から参照可能な型では、特定の基本型が拡張されます。 現時点では、このルールは、次の種類から派生した型を報告します。  
  
-   <xref:System.ApplicationException?displayProperty=fullName>  
  
-   <xref:System.Xml.XmlDocument?displayProperty=fullName>  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.Queue?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Stack?displayProperty=fullName>  
  
## <a name="rule-description"></a>規則の説明  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 1 のバージョンから新しい例外を派生させるが推奨されました<xref:System.ApplicationException>です。 推奨設定が変更され、新しい例外の派生元<xref:System.Exception?displayProperty=fullName>またはそのサブクラス内の 1 つ、<xref:System>名前空間。  
  
 サブクラスを作成しない<xref:System.Xml.XmlDocument>を基になるオブジェクト モデルまたはデータ ソースの XML ビューを作成するかどうか。  
  
### <a name="non-generic-collections"></a>非ジェネリック コレクション  
 使用させたり、拡張可能な場合、ジェネリック コレクション。 以前に出荷する場合を除き、コード内の非ジェネリック コレクションを拡張しません。  
  
 **不適切な使用例**  
  
```csharp  
public class MyCollection : CollectionBase  
{  
}  
  
public class MyReadOnlyCollection : ReadOnlyCollectionBase  
{  
}  
```  
  
 **正しい使用例**  
  
```csharp  
public class MyCollection : Collection<T>  
{  
}  
  
public class MyReadOnlyCollection : ReadOnlyCollection<T>  
{  
}  
```  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、別の基本型またはジェネリック コレクションから型を派生します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 違反に対するこの規則による警告は抑制しないでください<xref:System.ApplicationException>です。 安全にに関する違反に対するこの規則による警告は抑制<xref:System.Xml.XmlDocument>です。 コードが以前にリリースされた場合は、非ジェネリック コレクションについて警告を抑制しても安全です。