---
title: "1710: 識別子は正しいサフィックスをいなければなりません |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1710
- IdentifiersShouldHaveCorrectSuffix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectSuffix
- CA1710
ms.assetid: 2b8e6dce-b4e8-4a66-ba9a-6b79be5bfe8c
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4fd4f23ab77e2b810d5064bd45e9f7d530e9844e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca1710-identifiers-should-have-correct-suffix"></a>CA1710: 識別子は、正しいサフィックスを含んでいなければなりません
|||  
|-|-|  
|TypeName|IdentifiersShouldHaveCorrectSuffix|  
|CheckId|CA1710|  
|カテゴリ|Microsoft.Naming|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 識別子には、正しいサフィックスはありません。  
  
## <a name="rule-description"></a>規則の説明  
 慣例により、特定の基本型を拡張するか、特定のインターフェイス、またはこれらの型から派生した型を実装する型の名前には、基本データ型またはインターフェイスに関連付けられているサフィックスを持ちます。  
  
 名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージ コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。  
  
 次の表には、基本型とサフィックスが関連付けられているインターフェイスが一覧表示します。  
  
|基本型/インターフェイス|サフィックス|  
|--------------------------|------------|  
|<xref:System.Attribute?displayProperty=fullName>|属性|  
|<xref:System.EventArgs?displayProperty=fullName>|EventArgs|  
|<xref:System.Exception?displayProperty=fullName>|例外|  
|<xref:System.Collections.ICollection?displayProperty=fullName>|Collection|  
|<xref:System.Collections.IDictionary?displayProperty=fullName>|Dictionary|  
|<xref:System.Collections.IEnumerable?displayProperty=fullName>|Collection|  
|<xref:System.Collections.Queue?displayProperty=fullName>|コレクションまたはキュー|  
|<xref:System.Collections.Stack?displayProperty=fullName>|コレクションまたはスタック|  
|<xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>|Collection|  
|<xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|Dictionary|  
|<xref:System.Data.DataSet?displayProperty=fullName>|データセット|  
|<xref:System.Data.DataTable?displayProperty=fullName>|コレクションまたはデータ テーブル|  
|<xref:System.IO.Stream?displayProperty=fullName>|ストリーム|  
|<xref:System.Security.IPermission?displayProperty=fullName>|アクセス許可|  
|<xref:System.Security.Policy.IMembershipCondition?displayProperty=fullName>|状態|  
|イベント ハンドラーのデリゲート。|EventHandler|  
  
 型を実装する<xref:System.Collections.ICollection>はディクショナリ、スタック、またはキューを使用できる型の使用目的に関する有益情報を提供する名などがあります、データ構造の一般的な型とします。  
  
 型を実装する<xref:System.Collections.ICollection>は特定のアイテムのコレクションが 'Collection' の単語で終わる名前を持つとします。 たとえば、一連の<xref:System.Collections.Queue>'QueueCollection' という名前のオブジェクトが必要があります。 'Collection' サフィックスを使用して、コレクションのメンバーを列挙できることを示します、 `foreach` (`For Each`で[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ステートメントです。  
  
 型を実装する<xref:System.Collections.IDictionary>も実装している場合でも、単語"ディクショナリ"で終わる名前を持つ<xref:System.Collections.IEnumerable>または<xref:System.Collections.ICollection>です。 'Collection' および 'ディクショナリ' サフィックスの名前付け規則には、次の 2 つの列挙パターンを区別するためにユーザーが有効にします。  
  
 'Collection' サフィックス付きの型では、この列挙パターンに従います。  
  
```  
foreach(SomeType x in SomeCollection) { }  
```  
  
 'ディクショナリ' サフィックスを持つ型では、この列挙パターンに従います。  
  
```  
foreach(SomeType x in SomeDictionary.Values) { }  
```  
  
 A<xref:System.Data.DataSet>オブジェクトのコレクションから成る<xref:System.Data.DataTable>のコレクションで構成されたオブジェクト<xref:System.Data.DataColumn?displayProperty=fullName>と<xref:System.Data.DataRow?displayProperty=fullName>の他のオブジェクト。 これらのコレクションを実装<xref:System.Collections.ICollection>ベースを通じて<xref:System.Data.InternalDataCollectionBase?displayProperty=fullName>クラスです。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 型の名前を変更して、正しいサフィックスを付けるようにします。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 型が拡張される可能性がある場合や、さまざまな項目の任意のセットを保持する、汎用的なデータ構造体の場合は、'Collection' サフィックスを使用する警告を抑制しても安全です。 この場合、実装、パフォーマンス、またはデータ構造の他の特性に関する有益情報を提供する名必要があります (たとえば、BinaryTree)。 型が、特定の種類 (たとえば、StringCollection) のコレクションを表す場合、サフィックスを使用して型を列挙することが示されているためこの規則による警告は抑制しないでください、`foreach`ステートメントです。  
  
 他のサフィックスをこの規則による警告は抑制しないでください。 サフィックスにより、型名から明らかに目的の使用方法です。  
  
## <a name="related-rules"></a>関連規則  
 [CA1711: 識別子は、不適切なサフィックスを含むことはできません](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)  
  
## <a name="see-also"></a>関連項目  
 [属性](/dotnet/standard/design-guidelines/attributes)   
 [処理と、イベントを発生させる](/dotnet/standard/events/index)  