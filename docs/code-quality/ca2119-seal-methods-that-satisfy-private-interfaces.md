---
title: "Ca 2119: プライベート インターフェイスを満たすメソッドをシールします |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SealMethodsThatSatisfyPrivateInterfaces
- CA2119
helpviewer_keywords:
- CA2119
- SealMethodsThatSatisfyPrivateInterfaces
ms.assetid: 483d02e1-cfaf-4754-a98f-4116df0f3509
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f05b59ffc48b072d1a94ddfd405072d9663e6257
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca2119-seal-methods-that-satisfy-private-interfaces"></a>CA2119: プライベート インターフェイスを満たすメソッドをシールします
|||  
|-|-|  
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|  
|CheckId|CA2119|  
|カテゴリ|Microsoft.Security|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 継承可能なパブリック型のオーバーライド可能なメソッド実装を提供する、 `internal` (`Friend` Visual Basic で) インターフェイス。  
  
## <a name="rule-description"></a>規則の説明  
 インターフェイス メソッド アクセシビリティを持つパブリック、実装する型を変更することはできません。 内部のインターフェイスでは、インターフェイスを定義するアセンブリの外側に実装されるものではありません、コントラクトを作成します。 使用して、内部のインターフェイスのメソッドを実装するパブリック型、 `virtual` (`Overridable` Visual basic) 修飾子により、アセンブリの外側にある派生型でオーバーライドされるメソッド。 定義しているアセンブリ内の 2 番目の型は、メソッドを呼び出すし、内部専用のコントラクトが必要ですが、動作があります危険にさらされるときに、代わりに、外部のアセンブリでオーバーライドされたメソッドを実行します。 これには、セキュリティの脆弱性が作成されます。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、メソッド オーバーライドされないように、アセンブリの外側、次のいずれかを使用します。  
  
-   宣言する型を行う`sealed`(`NotInheritable` Visual Basic で)。  
  
-   宣言する型のアクセシビリティを変更して`internal`(`Friend` Visual Basic で)。  
  
-   すべてのパブリック コンス トラクターを宣言する型から削除します。  
  
-   メソッドの実装を使用せず、`virtual`修飾子です。  
  
-   メソッドを明示的に実装します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この警告を抑制する安全ではルールの場合、セキュリティの問題が存在しないことを注意深く確認はアセンブリの外部メソッドがオーバーライドされる場合、悪用される可能性があります。  
  
## <a name="example"></a>例  
 次の例は、型`BaseImplementation`、この規則に違反します。  
  
 [!code-cpp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_1.cpp)]
 [!code-csharp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_1.cs)]
 [!code-vb[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_1.vb)]  
  
## <a name="example"></a>例  
 次の例では、前の例の仮想メソッドの実装を利用します。  
  
 [!code-cpp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_2.cpp)]
 [!code-csharp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_2.cs)]
 [!code-vb[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_2.vb)]  
  
## <a name="see-also"></a>関連項目  
 [インターフェイス](/dotnet/csharp/programming-guide/interfaces/index)   
 [インターフェイス](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)