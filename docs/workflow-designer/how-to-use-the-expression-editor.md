---
title: "方法: 式エディターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Presentation.View.ExpressionTextBox.UI
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
caps.latest.revision: "13"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: b7deb3daed85c0c15d299052642abcb732ff12c2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-use-the-expression-editor"></a>式エディターを使用する方法
式エディターは、式を入力および評価する手段として、多くのワークフロー アクティビティで使用される[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] コントロールです。 式エディターには、IntelliSense、色付け、パラメーター情報、エラーを示す波線などの、本格的な IDE 編集機能が用意されています。 入力した式はコンパイラによって検証されます。 式が無効な場合は、エラー アイコンが表示されます。 エディターを開くことも、**式エディター**  ダイアログ ボックス。  
  
 式は、引数またはプロパティにバインドされたリテラル値または [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] コードです。 式には、新しい値を生成するための操作と組み合わされた値要素 (変数、定数、リテラル、プロパティなど) が含まれます。 アプリケーションが C# を使用したプログラムに含まれている場合でも、式の記述には VB.NET 構文が使用されます。 つまり、大文字小文字は区別しないを使用して比較を実行、1 つに等号 (「=」) (「= =」) ではなく、ブール演算子は、単語「と」とシンボルの代わりに「または」"(& a) (& a)"と"&#124; &#124;、および**何も行われません**の代わりに使用される**null**です。 式と演算子について[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]し、一部のサンプルでは、次を参照してください。 [Visual Basic の演算子よぶ式](http://go.microsoft.com/fwlink/?LinkId=186818)です。  
  
 **式エディター**ように動作します。  
  
-   フォーカスがない場合、式エディターは通常の TextBlock コントロールと同様の外観になります。  
  
-   フォーカスが式エディターに移ると、式エディター コントロールと同様の外観と動作になります。 フォーカスが失われると、通常の TextBlock と同様の外観に戻ります。  
  
-   再ホストされたワークフロー デザイナーで式エディターにフォーカスを設定した場合は、TextBox と同じように動作します。 再ホストされたワークフロー デザイナーでフォーカスが失われると、式エディターは、通常の TextBlock と同様の外観に戻ります。  
  
> [!NOTE]
>  式エディター用の IntelliSense は、[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 内でのみ使用できます。 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] および再ホストのシナリオではいずれも、入力した式がコンパイラによって検証され、式が無効な場合は、式エディターにエラー アイコンが表示されます。  
  
### <a name="using-the-expression-editor"></a>式エディターの使用  
  
1.  [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] で新規または既存のワークフロー プロジェクトを開きます。  
  
2.  ワークフローに <xref:System.Activities.Statements.Assign> などのアクティビティを追加します。  
  
    > [!NOTE]
    >  式エディターを使用できるワークフロー アクティビティは複数あります。 変数デザイナー、引数デザイナー、および動的引数デザイナーには、式 TextBlock も表示されます。 ここでは、例として <xref:System.Activities.Statements.Assign> アクティビティを使用しています。  
  
3.  <xref:System.Activities.Statements.Assign> アクティビティのアクティビティ デザイナーで、左側の式エディターをクリックします。  
  
     灰色のウォーターマークの文字列**\<に >**と **\<VB の式を入力 >**で式エディターのテキスト文字列を既定値には、<xref:System.Activities.Statements.Assign>アクティビティ。  
  
4.  式を入力します。 文字列を入力する場合は、文字列を引用符で囲みます。 式の引数を変数にバインドする場合は、引用符を省略してください。  
  
     式を入力し終えたら、式エディターの外部を選択して、デザイナーの他の部分にフォーカスを移動させます。 この操作により、既に説明したように、コンパイラによって式が検証されます。  
  
     式を入力または編集する方法として、プロパティ グリッドのプロパティ名の横にある省略記号をクリックするという方法もあります。 これが開き、**式エディター**  ダイアログ ボックス。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>