---
title: "1309: ordinal StringComparison を使用します |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ba777ea4cd272a1392413a2ecbb52b9f45a3d71b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: 順序を示す StringComparison を使用します
|||  
|-|-|  
|TypeName|UseOrdinalStringComparison|  
|CheckId|CA1309|  
|カテゴリ|Microsoft.Globalization|  
|互換性に影響する変更点|なし|  
  
## <a name="cause"></a>原因  
 非言語的な文字列比較操作が設定されていない、<xref:System.StringComparison>またはにパラメーターを**序数**または**OrdinalIgnoreCase**です。  
  
## <a name="rule-description"></a>規則の説明  
 多くの文字列操作、最も重要な<xref:System.String.Compare%2A?displayProperty=fullName>と<xref:System.String.Equals%2A?displayProperty=fullName>、メソッドを受け入れるオーバー ロードを提供するようになりました、<xref:System.StringComparison?displayProperty=fullName>をパラメーターとしての列挙値。  
  
 いずれかを指定すると**StringComparison.Ordinal**または**StringComparison.OrdinalIgnoreCase**、非言語的な文字列の比較になります。 つまり、比較が決定されます、自然言語に固有の機能は無視されます。 つまり、上の決定は、単純なバイト比較に基づいており、大文字と小文字または同等の表のカルチャでパラメーター化されるを無視します。 いずれかにパラメーターを明示的に設定してその結果、 **StringComparison.Ordinal**または**StringComparison.OrdinalIgnoreCase**、コード多くの場合、速度の向上が正しいかどうか、なりが信頼性の高い。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、文字列比較のメソッドを変更を受け入れるオーバー ロードに、<xref:System.StringComparison?displayProperty=fullName>列挙体をパラメーターとしてどちらかを指定して**序数**または**OrdinalIgnoreCase**です。 たとえば、`String.Compare(str1, str2)` を `String.Compare(str1, str2, StringComparison.Ordinal)` に変更します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 ライブラリまたはアプリケーションは、限定されたローカル ユーザーのまたは現在のカルチャのセマンティクスを使用する必要がある場合は、この規則による警告を抑制しても安全です。  
  
## <a name="see-also"></a>関連項目  
 [グローバリゼーションに関する警告](../code-quality/globalization-warnings.md)   
 [CA1307: StringComparison の指定](../code-quality/ca1307-specify-stringcomparison.md)