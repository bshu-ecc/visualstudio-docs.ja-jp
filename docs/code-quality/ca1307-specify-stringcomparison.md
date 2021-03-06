---
title: "Ca 1307: StringComparison の指定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 61d8ca557bfc55e3488a35e82f0242f931c51ed4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: StringComparison の指定
|||  
|-|-|  
|TypeName|SpecifyStringComparison|  
|CheckId|CA1307|  
|カテゴリ|Microsoft.Globalization|  
|互換性に影響する変更点|なし|  
  
## <a name="cause"></a>原因  
 文字列比較操作が設定されていないメソッドのオーバー ロードを使用して、<xref:System.StringComparison>パラメーター。  
  
## <a name="rule-description"></a>規則の説明  
 多くの文字列操作、最も重要な<xref:System.String.Compare%2A>と<xref:System.String.Equals%2A>メソッドを受け入れるオーバー ロードを提供する、<xref:System.StringComparison>列挙値をパラメーターとして。  
  
 オーバー ロードするたびに行うためにかかるが存在する場合、<xref:System.StringComparison>パラメーターをこのパラメーターを受け取らないオーバー ロードの代わりに使用する必要があります。 このパラメーターを明示的に設定するには、コードは、多くの場合、わかりやすくなり、保守が簡単にします。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、文字列比較メソッドを許容するオーバー ロードに変更、<xref:System.StringComparison>列挙体をパラメーターとして。 例: 変更`String.Compare(str1, str2)`に`String.Compare(str1, str2, StringComparison.Ordinal)`です。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 ライブラリまたはアプリケーションは、限定されたローカル ユーザーのためのものでは、してためにローカライズされない場合は、この規則による警告を抑制しても安全です。  
  
## <a name="see-also"></a>関連項目  
 [グローバリゼーションに関する警告](../code-quality/globalization-warnings.md)   
 [CA1309: 順序を示す StringComparison を使用します](../code-quality/ca1309-use-ordinal-stringcomparison.md)