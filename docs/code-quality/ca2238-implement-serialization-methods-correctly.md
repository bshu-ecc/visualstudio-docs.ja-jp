---
title: "Ca 2238: シリアル化メソッドを正しく実装 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
helpviewer_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
ms.assetid: 00882cf9-e10d-4d40-9126-3e6753e3c934
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9ca904e9259855127825b594db80cdc3524d53ec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ca2238-implement-serialization-methods-correctly"></a>CA2238: シリアル化メソッドを正しく実装します
|||  
|-|-|  
|TypeName|ImplementSerializationMethodsCorrectly|  
|CheckId|CA2238|  
|カテゴリ|Microsoft.Usage|  
|互換性に影響する変更点|– メソッドは、アセンブリ外部から参照できる場合です。<br /><br /> なしの場合、メソッドは、アセンブリ外部から参照ではありません。|  
  
## <a name="cause"></a>原因  
 シリアル化イベントを処理するメソッドに、適切なシグネチャ、戻り値の型、または参照範囲がありません。  
  
## <a name="rule-description"></a>規則の説明  
 メソッドは、シリアル化イベントのハンドラーをシリアル化イベント属性は次のいずれかの操作を適用することによって示されます。  
  
-   <xref:System.Runtime.Serialization.OnSerializingAttribute?displayProperty=fullName>  
  
-   <xref:System.Runtime.Serialization.OnSerializedAttribute?displayProperty=fullName>  
  
-   <xref:System.Runtime.Serialization.OnDeserializingAttribute?displayProperty=fullName>  
  
-   <xref:System.Runtime.Serialization.OnDeserializedAttribute?displayProperty=fullName>  
  
 シリアル化イベントのハンドラーが型の 1 つのパラメーターを受け取る<xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>、return `void`、いて`private`表示します。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、シグネチャ、戻り値の型、またはシリアル化イベント ハンドラーの可視性を修正します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告は抑制しないでください。  
  
## <a name="example"></a>例  
 次の例は、イベント ハンドラーを正しく宣言されているシリアル化に示します。  
  
 [!code-vb[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/VisualBasic/ca2238-implement-serialization-methods-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/CSharp/ca2238-implement-serialization-methods-correctly_1.cs)]  
  
## <a name="related-rules"></a>関連規則  
 [CA2236: ISerializable 型で基本クラス メソッドを呼び出します](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: ISerializable を正しく実装します](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2235: すべてのシリアル化不可能なフィールドを設定します](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2237: ISerializable 型を SerializableAttribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: オプションのフィールドに逆シリアル化メソッドを指定します](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: シリアル化コンストラクターをセキュリティで保護します](../code-quality/ca2120-secure-serialization-constructors.md)