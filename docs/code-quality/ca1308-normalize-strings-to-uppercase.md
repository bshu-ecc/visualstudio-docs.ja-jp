---
title: ": Ca 1308 文字列を大文字に |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8c9746d150fb2a47b1ce874ad003afd86d178e9a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: 文字列を大文字に標準化します
|||  
|-|-|  
|TypeName|NormalizeStringsToUppercase|  
|CheckId|CA1308|  
|カテゴリ|Microsoft.Globalization|  
|互換性に影響する変更点|なし|  
  
## <a name="cause"></a>原因  
 操作は、小文字の文字列を正規化します。  
  
## <a name="rule-description"></a>規則の説明  
 文字列は大文字に正規化する必要があります。 少数の文字が小文字に変換した、ラウンド トリップさせることはできません。 ラウンド トリップさせるのには、文字変換ロケールは 1 つから、データを表す文字が異なる別のロケールに正確にするための手段は、変換後の文字から元の文字を取得します。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 文字列を変換できるように文字列を小文字に変換する操作を変更する代わりに大文字にします。 たとえば、`String.ToLower(CultureInfo.InvariantCulture)` を `String.ToUpper(CultureInfo.InvariantCulture)` に変更します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 (たとえば、UI に表示する場合に) 結果に基づいてセキュリティ上の決定を行わない場合に警告メッセージを抑制しても安全です。  
  
## <a name="see-also"></a>関連項目  
 [グローバリゼーションに関する警告](../code-quality/globalization-warnings.md)