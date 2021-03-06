---
title: "Ca 2126: 型のリンク要求には継承要求が必要です |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 254fd15f97afe69f927bb8a1aae1954105776641
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: 型のリンク要求には継承要求が必要です
|||  
|-|-|  
|TypeName|TypeLinkDemandsRequireInheritanceDemands|  
|CheckId|CA2126|  
|カテゴリ|Microsoft.Security|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 パブリックのシールされていない型が保護されているリンク要求とオーバーライド可能なメソッドがあり、型でも、メソッドが継承確認要求で保護されています。  
  
## <a name="rule-description"></a>規則の説明  
 メソッドまたはその宣言する型にリンク確認要求では、直接の呼び出し元のメソッドの指定した権限を持っている必要があります。 メソッドの継承確認要求では、オーバーライドするメソッドを指定した権限を持っている必要があります。 型の継承確認要求では、指定した権限を持っているために派生クラスが必要です。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、種類またはリンク確認要求と同じアクセス許可の継承確認要求を持つメソッドをセキュリティで保護します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告は抑制しないでください。  
  
## <a name="example"></a>例  
 次の例は、規則に違反する型を示しています。  
  
 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]  
  
## <a name="related-rules"></a>関連規則  
 [CA2108: 値型での宣言セキュリティをレビューします](../code-quality/ca2108-review-declarative-security-on-value-types.md)  
  
 [CA2112: セキュリティで保護された型はフィールドを公開してはなりません](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA2122: リンク確認要求で間接的にメソッドを公開しないでください](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)  
  
 [CA2123: オーバーライドのリンク確認要求は基本と同様にします](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)  
  
## <a name="see-also"></a>関連項目  
 [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)   
 [継承確認要求](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)   
 [リンク確認要求](/dotnet/framework/misc/link-demands)   
 [確認要求](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48)