---
title: "フォーム領域を Outlook メッセージ クラスに関連付ける |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTO.NewFormRegionWizard.InvalidMessageClassName
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FormRegionMessageClassAttribute
- form regions [Office development in Visual Studio], message classes
ms.assetid: e2db8d61-fd5f-4059-beec-33b66970f520
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3346b5cf096c523c9eb2c066d87a85e0d57efd94
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="associating-a-form-region-with-an-outlook-message-class"></a>フォーム領域の Outlook メッセージ クラスへの関連付け
  Microsoft Office Outlook アイテムは、各アイテムのメッセージ クラスとフォーム領域を関連付けることによって、フォーム領域を表示を指定することができます。 たとえば、メール アイテムの下部にフォーム領域を追加する場合、ipm フォーム領域を関連付けることができます。メッセージ クラスに注意してください。  
  
 メッセージ クラスとフォーム領域を関連付ける、内のメッセージ クラス名を指定、**新しい Outlook フォーム領域**ウィザードまたはフォーム領域ファクトリ クラスに属性を適用します。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="understanding-outlook-message-classes"></a>Outlook メッセージ クラスをについてください。  
 Outlook メッセージ クラスは、Outlook アイテムの種類を識別します。 次の表では、8 種類の標準項目とのメッセージ クラス名の一覧表示します。  
  
|Outlook アイテムの種類|メッセージ クラス名|  
|-----------------------|------------------------|  
|AppointmentItem|IPM です。予定|  
|ContactItem|IPM です。お問い合わせください。|  
|配布リスト|IPM です。配布リスト|  
|JournalItem|IPM です。アクティビティ|  
|MailItem|IPM です。注意してください。|  
|PostItem|IPM です。Post、または IPM です。Post.RSS|  
|TaskItem|IPM です。タスク|  
  
 カスタム メッセージ クラスの名前を指定することもできます。 カスタム メッセージ クラスは、Outlook で定義したカスタムのフォームを識別します。  
  
> [!NOTE]  
>  置換およびすべて置換フォーム領域は、新しいカスタム メッセージ クラス名を指定することができます。 既存のカスタム フォームのメッセージ クラス名を使用する必要はありません。 カスタム メッセージ クラスの名前は一意である必要があります。 次のような名前付け規則を使用するには名前が一意であることを確認する方法: \< *StandardMessageClassName*>.\<*会社*>.\<*MessageClassName*> (例: IPM です。Note.Contoso.MyMessageClass)。  
  
## <a name="associating-a-form-region-with-an-outlook-message-class"></a>フォーム領域の Outlook メッセージ クラスへの関連付け  
 メッセージ クラスとフォーム領域を関連付けるには 2 つの方法があります。  
  
-   使用して、**新しい Outlook フォーム領域**ウィザード。  
  
-   クラスの属性を適用します。  
  
### <a name="using-the-new-outlook-form-region-wizard"></a>新しい Outlook フォーム領域ウィザードを使用します。  
 最後のページで、**新しい Outlook フォーム領域**ウィザードで、標準のメッセージ クラスを選択し、フォーム領域に関連付けるカスタム メッセージ クラスの名前を入力することができます。  
  
 標準のメッセージ クラスは、フォーム領域を全体のフォームまたはフォームの既定のページを置換する場合はご利用いただけません。 フォームをフォームに新しいページを追加するか、フォームの下部に追加されるは標準のメッセージ クラス名を指定できます。 詳細については、次を参照してください。[する方法: フォーム領域を Outlook アドイン プロジェクトに追加](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)です。  
  
 1 つまたは複数のカスタム メッセージ クラスを含めるには、その名前を入力、**このフォーム領域を表示するカスタム メッセージ クラス?**ボックス。  
  
 入力した名前は、以下のガイドラインに従う必要があります。  
  
-   メッセージの完全修飾クラス名を使用して (例:"IPM です。Note.Contoso") です。  
  
-   セミコロンを使用して、複数のメッセージ クラス名を区切ります。  
  
-   "IPM など、標準の Outlook メッセージ クラスを含めないでください。注"または"IPM です。Contact"です。 "IPM などのカスタム メッセージ クラスのみを含める.Note.Contoso"です。  
  
-   単独で、基本メッセージ クラスを指定して (例:"IPM") です。  
  
-   各メッセージ クラス名は、256 文字をを超えてはなりません。  
  
 **新しい Outlook フォーム領域**をクリックすると、ウィザードは、入力の形式を検証**完了**です。  
  
> [!NOTE]  
>  **新しい Outlook フォーム領域**ウィザードが提供するメッセージ クラス名が正しいか、有効なことを確認していません。  
  
 ウィザードを完了したときに、**新しい Outlook フォーム領域**ウィザードでは、指定されたメッセージ クラス名を含むフォーム領域クラスに属性が適用されます。 これらの属性を手動で適用することもできます。  
  
### <a name="applying-class-attributes"></a>クラスの属性を適用します。  
 完了した後、Outlook メッセージ クラスとフォーム領域を関連付けることができます、**新しい Outlook フォーム領域**ウィザード。 これを行うには、フォーム領域ファクトリ クラスに属性を適用します。  
  
 次の例は 2 つ<xref:Microsoft.Office.Tools.Outlook.FormRegionMessageClassAttribute>という名前のフォーム領域ファクトリ クラスに適用されている属性`myFormRegion`です。 最初の属性は、フォーム領域をメール メッセージの形式の標準的なメッセージ クラスに関連付けます。 2 番目の属性は、という名前のカスタム メッセージ クラスをフォーム領域を関連付けます`IPM.Task.Contoso`です。  
  
 [!code-vb[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Attributes/FormRegion1.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Attributes/FormRegion1.cs#1)]  
  
 属性は、次のガイドラインに準拠する必要があります。  
  
-   カスタム メッセージ クラスの完全修飾クラス名を使用して (例:"IPM です。Note.Contoso") です。  
  
-   単独で、基本メッセージ クラスを指定して (例:"IPM") です。  
  
-   各メッセージ クラス名は、256 文字をを超えてはなりません。  
  
-   全体のフォームまたはフォームの既定のページ、フォーム領域が置き換えられた場合は、標準のメッセージ クラスの名前を含めないでください。 フォームをフォームに新しいページを追加するか、フォームの下部に追加されるは標準のメッセージ クラス名を指定できます。 詳細については、次を参照してください。[する方法: フォーム領域を Outlook アドイン プロジェクトに追加](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)です。  
  
 Visual Studio は、プロジェクトをビルドするときに、メッセージ クラス名の形式を検証します。  
  
> [!NOTE]  
>  Visual Studio では、提供するメッセージ クラス名が正しいか、有効なことは検証されません。  
  
## <a name="see-also"></a>関連項目  
 [実行時にフォーム領域へのアクセス](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook フォーム領域の作成](../vsto/creating-outlook-form-regions.md)   
 [チュートリアル: Outlook フォーム領域のデザイン](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Outlook フォーム領域の作成に関するガイドライン](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [フォームの名前とメッセージ クラスの概要](http://msdn.microsoft.com/library/office/ff867629.aspx)   
 [Outlook フォームと項目を連携させる方法](http://msdn.microsoft.com/library/office/ff869706.aspx)  
  
  