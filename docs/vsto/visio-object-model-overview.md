---
title: "Visio オブジェクト モデルの概要 |Microsoft ドキュメント"
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
- Visio [Office development in Visual Studio], object model
- object models [Office development in Visual Studio], Office
- object models [Office development in Visual Studio], Visio
- objects [Office development in Visual Studio], Office object models
- Office object models
- Visio object model
ms.assetid: 11f0ae0c-feff-46c7-9885-b968391718f7
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 732a270564c40c4ca20952d86abb8618f9a060f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="visio-object-model-overview"></a>Visio オブジェクト モデルの概要
  Visio オブジェクト モデルと対話することにより、Microsoft Office Visio 用の Office ソリューションを開発できます。 このオブジェクト モデルは、visio では、プライマリ相互運用機能アセンブリで提供されで定義するクラスとインターフェイスから成ります。  
  
 ここでは、Visio オブジェクト モデルの概要を簡単に説明します。 Office プロジェクトでタスクを実行するために Visio オブジェクト モデルを使用する方法については、次のトピックを参照してください。  
  
-   [Visio 図面の操作](../vsto/working-with-visio-documents.md)  
  
-   [Visio の図形の操作](../vsto/working-with-visio-shapes.md)  
  
## <a name="understanding-the-visio-object-model"></a>Visio オブジェクト モデルについて  
 Visio では、多くのオブジェクトが操作対象になります。 これらのオブジェクトは、ユーザー インターフェイスとほぼ同様の階層形式で編成されています。 階層の最上位にあるのは、 [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx) オブジェクトです。 このオブジェクトは、Visio の現在のインスタンスを表します。 Microsoft.Office.Interop.Visio.Document と Microsoft.Office.Interop.Visio.Page オブジェクトだけでなく、Microsoft.Office.Interop.Visio.Documents Microsoft.Office.Interop.Visio.Application オブジェクトが含まれています、Microsoft.Office.Interop.Visio.Pages コレクションです。 これらのオブジェクトとコレクションにはそれぞれ数多くのメソッドとプロパティがあり、それらにアクセスしてオブジェクトを処理したり、オブジェクトと対話したりできます。  
  
 詳細については、 [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx)、 [Microsoft.Office.Interop.Visio.Document](https://msdn.microsoft.com/library/office/ff765575.aspx)、および [Microsoft.Office.Interop.Visio.Page](https://msdn.microsoft.com/library/office/ff767035.aspx) の各オブジェクト、 [Microsoft.Office.Interop.Visio.Documents](https://msdn.microsoft.com/library/office/ff768812.aspx) および [Microsoft.Office.Interop.Visio.Pages](https://msdn.microsoft.com/library/office/ff766165.aspx) の各コレクションの VBA リファレンス ドキュメントを参照してください。  
  
 この後のセクションでは、最上位レベルのオブジェクトとそれらの相互関係について、簡単に説明します。 このようなオブジェクトには次の 4 つがあります。  
  
-   Application オブジェクト  
  
-   Document オブジェクト  
  
-   Page オブジェクト  
  
### <a name="application-object"></a>Application オブジェクト  
 Microsoft.Office.Interop.Visio.Application オブジェクトは、Visio アプリケーションを表し、他のオブジェクトのすべての親であります。 そのメンバーは、通常、Visio 全体に適用されます。 プロパティと、Microsoft.Office.Interop.Visio.Application および Microsoft.Office.Interop.Visio.ApplicationSettings オブジェクトのメソッドを使用するには、Visio の環境を制御します。  
  
 VSTO アドイン プロジェクトで使用して、Microsoft.Office.Interop.Visio.Application オブジェクトにアクセスすることができます、`Application`のフィールド、`ThisAddIn`クラスです。 詳細については、「 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)」を参照してください。  
  
### <a name="document-object"></a>Document オブジェクト  
 Microsoft.Office.Interop.Visio.Document オブジェクトは、Visio プログラミングの中心です。 これは、図面、ステンシル、またはテンプレート ファイルを表します。 Visio 図面を開いたり、新しいドキュメントを作成したりすると、オブジェクトを生成する、新しい Microsoft.Office.Interop.Visio.Document Microsoft.Office.Interop.Visio.Application オブジェクトの Microsoft.Office.Interop.Visio.Documents コレクションに追加されています。.  
  
 フォーカスがある文書は、作業中のドキュメントと呼ばれます。 Microsoft.Office.Interop.Visio.Application オブジェクトの Microsoft.Office.Interop.Visio.Application.ActiveDocument プロパティによって表されます。  
  
### <a name="page-object"></a>Page オブジェクト  
 Microsoft.Office.Interop.Visio.Page オブジェクトでは、前景ページまたは背景ページの描画領域を表します。 Microsoft.Office.Interop.Visio.Page.Background プロパティを使用して、ページが、フォア グラウンドまたはバック グラウンドのページであるかどうかを判別することができます。  
  
 図形を作成するには、Microsoft.Office.Interop.Visio.Page.DrawSpline と Microsoft.Office.Interop.Visio.Page.DrawOval メソッドが含まれているメソッドを使用することができます。 また、ステンシルからマスターを取得し、Microsoft.Office.Interop.Visio.Page.Drop または Microsoft.Office.Interop.Visio.Page.DropMany メソッドを使用して図形をページに配置します。  
  
## <a name="using-the-visio-object-model-documentation"></a>Visio オブジェクト モデル ドキュメントの使用  
 Visio オブジェクト モデルの詳細については、Visio の VBA オブジェクト モデルのリファレンスを参照してください。 VBA オブジェクト モデルのリファレンス ドキュメントでは、Visual Basic for Applications (VBA) コードに公開される Visio オブジェクト モデルについて説明しています。 詳細については、「 [Visio 2010 Object Model Reference (Visio 2010 オブジェクト モデル リファレンス)](http://go.microsoft.com/fwlink/?LinkId=199775)」を参照してください。  
  
 VBA オブジェクト モデルのリファレンス内のオブジェクトとメンバーはすべて、Visio プライマリ相互運用機能アセンブリ (PIA) の型とメンバーに対応します。 たとえば、VBA オブジェクト モデルのリファレンス内のドキュメント オブジェクトは、Visio PIA の Microsoft.Office.Interop.Visio.Document 型に対応します。 VBA オブジェクト モデルのリファレンスでは、ほとんどのプロパティ、メソッド、およびイベントのコード例を紹介しています。ただし、Visual Studio を使用して作成した Visio VSTO アドイン プロジェクトでこのリファレンス内の VBA コードを使用するには、それらを Visual Basic または Visual C# に変換する必要があります。  
  
> [!NOTE]  
>  現在のところ、Visio プライマリ相互運用機能アセンブリに関するリファレンス ドキュメントは提供されていません。  
  
 Visio ソリューションの作成に関連するコード例と追加のツールについては「 [Visio 2010 Software Development Kit (Visio 2010 ソフトウェア開発キット)](http://go.microsoft.com/fwlink/?LinkId=196501)」を参照してください。  
  
### <a name="additional-types-in-primary-interop-assemblies"></a>プライマリ相互運用機能アセンブリの追加の型  
 実装の違いにより VBA には表示されないプライマリ相互運用機能アセンブリの型があります。 VBA では、直接使用できるオブジェクトとメンバーだけを含む Visio オブジェクト モデルのビューが提供されます。 プライマリ相互運用機能アセンブリは同じオブジェクト モデルを公開しますが、それには、COM オブジェクト モデルのオブジェクトをマネージ コードに変換する、その他のインターフェイス、クラス、およびメンバーも含まれています。 これらの追加の項目は、コードで直接使用するためのものではありません。  
  
 詳細については、「 [Overview of Classes and Interfaces in the Office Primary Interop Assemblies (Office プライマリ相互運用機能アセンブリのクラスとインターフェイスの概要)](http://go.microsoft.com/fwlink/?LinkId=189592) オブジェクトと [Office Primary Interop Assemblies](../vsto/office-primary-interop-assemblies.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [Visio ソリューション](../vsto/visio-solutions.md)   
 [Visio 図面の操作](../vsto/working-with-visio-documents.md)   
 [Visio の図形の操作](../vsto/working-with-visio-shapes.md)  
  
  