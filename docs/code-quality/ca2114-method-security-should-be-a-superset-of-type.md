---
title: "Ca 2114: メソッドのセキュリティは型のスーパー セットをする必要があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9784ae650a411ef4fe5086ae8bf756147fd2365
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: メソッドのセキュリティは型のスーパーセットにします
|||  
|-|-|  
|TypeName|MethodSecurityShouldBeASupersetOfType|  
|CheckId|CA2114|  
|カテゴリ|Microsoft.Security|  
|互換性に影響する変更点|あり|  
  
## <a name="cause"></a>原因  
 型は、宣言セキュリティおよびそのメソッドのいずれかが、同じセキュリティ操作の宣言セキュリティおよびセキュリティ アクションは[リンク確認要求](/dotnet/framework/misc/link-demands)または[継承確認要求](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)、およびアクセス許可チェックの種類によっては、メソッドによってチェックする権限のサブセットではありません。  
  
## <a name="rule-description"></a>規則の説明  
 メソッドには、同じアクションに対してメソッド レベルと型レベルの宣言セキュリティの両方を持つべきはありません。 2 つのチェックは結合はされません。メソッド レベルの要求のみが適用されます。 型のアクセス許可を要求する場合など、 `X`、アクセス許可を要求のメソッドのいずれかと`Y`、コードにアクセス許可がない`X`メソッドを実行します。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 操作の両方が必須であるかどうかを確認するコードを確認します。 両方のアクションが必要な場合は、メソッド レベルのアクションが、型レベルで指定したセキュリティが含まれていることを確認してください。 種類のアクセス許可を要求する場合など、 `X`、し、そのメソッドは、アクセス許可を要求する必要がありますも`Y`、メソッドが明示的に要求する必要があります`X`と`Y`です。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 メソッドは、型で指定されたセキュリティを必要としない場合は、この規則による警告を抑制するのには安全です。 ただし、これは通常のシナリオではありません、慎重に設計レビューの必要があります。  
  
## <a name="example"></a>例  
 次の例では、環境のアクセス許可を使用して、この規則違反の危険性を示します。 この例では、アプリケーション コードは、型に必要な権限を拒否する前にセキュリティで保護された型のインスタンスを作成します。 脅威の実際のシナリオでは、別の方法をオブジェクトのインスタンスを取得する必要があります。  
  
 次の例では、ライブラリの要求は、型の書き込みアクセス許可し、メソッドに対する読み取りアクセス許可。  
  
 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]  
  
## <a name="example"></a>例  
 次のアプリケーション コードでは、型レベルのセキュリティ要件を満たしていない場合でも、メソッドを呼び出すことによって、ライブラリの脆弱性を示します。  
  
 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]  
  
 この例を実行すると、次の出力が生成されます。  
  
 **[すべてのアクセス許可]個人情報: 6/16/1964 12時 00分: 00 AM**  
**[書き込みアクセス許可がありません (の型によって要求)]個人情報: 6/16/1964 12時 00分: 00 AM**  
**[読み取りアクセス許可がありません (メソッドで必要)]個人情報にアクセスできませんでした。 要求が失敗しました。**   
## <a name="see-also"></a>関連項目  
 [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)   
 [継承確認要求](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)   
 [リンク確認要求](/dotnet/framework/misc/link-demands)   
 [データとモデリング](/dotnet/framework/data/index)