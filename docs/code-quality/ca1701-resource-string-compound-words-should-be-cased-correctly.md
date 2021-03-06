---
title: "Ca 1701: リソース文字列の複合語を正しく使い分ける |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ResourceStringCompoundWordsShouldBeCasedCorrectly
- CA1701
helpviewer_keywords:
- CA1701
- ResourceStringCompoundWordsShouldBeCasedCorrectly
ms.assetid: 4ddbe09f-24b8-4c47-9373-a06f4487ca0d
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4dee5b21724944ea26e89c2cd1ace556f1377848
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701: リソース文字列の複合語は、大文字と小文字を正しく区別しなければなりません
|||  
|-|-|  
|TypeName|ResourceStringCompoundWordsShouldBeCasedCorrectly|  
|CheckId|CA1701|  
|カテゴリ|Microsoft.Naming|  
|互換性に影響する変更点|なし|  
  
## <a name="cause"></a>原因  
 リソース文字列には、正しく大文字と小文字に表示されていない複合語が含まれています。  
  
## <a name="rule-description"></a>規則の説明  
 リソース文字列内の各単語は、大文字と小文字に基づいてトークンに分割されます。 Microsoft スペル チェック ライブラリは、隣接する 2 つのトークンの組み合わせを個別にチェックします。 それらが認識されると、その語はこの規則への違反となります。 違反を引き起こす複合語には、"CheckSum"と「マルチパート」は、使い分ける"Checksum"および「マルチパート」としてそれぞれがあります。 以前の一般的な使用法によりいくつかの例外が、そのルールに組み込まれている、単一の語でありながら"Toolbar"、"Filename"2 つの語として使い分けることなどです。 この例では"ToolBar"、"FileName"がフラグが付けられます。  
  
 名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージ コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 大文字と小文字を正しく区別できるように、単語を変更します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 複合語の両方の部分は、辞書によって認識され、その目的は 2 つの単語を使用する場合は、この規則による警告を抑制しても安全です。  
  
 スペル チェックの辞書に複合語を追加することもできます。 カスタム辞書で単語では、違反が発生しません。 詳細については、次を参照してください。[する方法: コード分析辞書をカスタマイズ](../code-quality/how-to-customize-the-code-analysis-dictionary.md)です。  
  
## <a name="related-rules"></a>関連規則  
 [CA1702: 複合語では、大文字と小文字が正しく区別されなければなりません](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
 [CA1709: 識別子では、大文字と小文字が正しく区別されなければなりません](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 識別子は、大文字と小文字の区別以外にも相違していなければなりません](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
## <a name="see-also"></a>関連項目  
 [大文字と小文字の表記規則](/dotnet/standard/design-guidelines/capitalization-conventions)   
 [名前付けのガイドライン](/dotnet/standard/design-guidelines/naming-guidelines)