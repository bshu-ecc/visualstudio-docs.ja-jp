---
title: "方法: プログラムによってワークシートの保護を解除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
ms.assetid: 034688d2-eda7-4b4a-bcc2-d0999ff879a4
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a5d38dacb07cfce6cae2f2b83a68c7090542cac8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>方法: プログラムによってワークシートの保護を解除する
  プログラムを使用して、Microsoft Office Excel ワークシートから保護を削除できます。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 次の例では、変数 `getPasswordFromUser`を使用して、ユーザーから取得したパスワードを格納します。  
  
### <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>ドキュメント レベルのカスタマイズでワークシートの保護を解除するには  
  
1.  ワークシートの <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> メソッドを呼び出して、必要に応じてパスワードを渡します。 この例では、 `Sheet1`という名前のワークシートを操作していると仮定します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]  
  
### <a name="to-unprotect-a-worksheet-in-an-vsto-add-in"></a>VSTO アドインで、ワークシートの保護を解除するには  
  
1.  アクティブなワークシートの <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> メソッドを呼び出して、必要に応じてパスワードを渡します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]  
  
## <a name="see-also"></a>関連項目  
 [ワークシートの操作](../vsto/working-with-worksheets.md)   
 [方法: プログラムによってワークシートを保護します。](../vsto/how-to-programmatically-protect-worksheets.md)   
 [方法: プログラムによってブックを保護します。](../vsto/how-to-programmatically-protect-workbooks.md)   
 [方法: プログラムによってワークシートを非表示](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Office プロジェクト内のオブジェクトへのグローバル アクセス](../vsto/global-access-to-objects-in-office-projects.md)  
  
  