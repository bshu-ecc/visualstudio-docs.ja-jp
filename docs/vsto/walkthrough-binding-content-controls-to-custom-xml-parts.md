---
title: "チュートリアル: カスタム XML 部分へのコンテンツ コントロールのバインド |Microsoft ドキュメント"
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
- PlainTextContentControl, binding to a custom XML part
- custom XML parts, binding to content controls
- content controls [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], content controls
- DropDownListContentControl, binding items to a custom XML part
- DatePickerContentControl, binding to a custom XML part
ms.assetid: 10d67769-6157-4703-a10c-d33e988f9095
caps.latest.revision: "51"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 252bbce784e412282f6092afdc53905faeb947d0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-binding-content-controls-to-custom-xml-parts"></a>チュートリアル : カスタム XML 部分へのコンテンツ コントロールのバインド
  このチュートリアルでは、Word のドキュメント レベルのカスタマイズで、コンテンツ コントロールを同じ文書内の XML データにバインドする方法を説明します。  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word では、という名前の XML データを格納することができます*カスタム XML 部分*ドキュメントにします。 このデータの表示は、カスタム XML 部分の要素にコンテンツ コントロールをバインドすることによって制御できます。 このチュートリアルで例として示す文書のカスタム XML 部分には、従業員情報が格納されています。 この文書を開くと、XML 要素の値がコンテンツ コントロールに表示されます。 コンテンツ コントロール内のテキストに加えた変更は、カスタム XML 部分に保存されます。  
  
 このチュートリアルでは、次の作業について説明します。  
  
-   デザイン時におけるドキュメント レベルのプロジェクトの Word 文書へのコンテンツ コントロールの追加  
  
-   XML データ ファイルと、コンテンツ コントロールにバインドする要素を定義する XML スキーマを作成する。  
  
-   デザイン時に XML スキーマを文書に添付する。  
  
-   実行時に XML ファイルの内容を文書内のカスタム XML 部分に追加する。  
  
-   コンテンツ コントロールをカスタム XML 部分の要素にバインドする。  
  
-   <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> を XML スキーマに定義された値にバインドする。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word。  
  
## <a name="creating-a-new-word-document-project"></a>新しい Word 文書プロジェクトを作成する  
 このチュートリアルで使用する Word 文書を作成します。  
  
#### <a name="to-create-a-new-word-document-project"></a>Word 文書プロジェクトを作成するには  
  
1.  名前の Word 文書プロジェクトを作成**EmployeeControls**です。 ソリューションの新しい文書を作成します。 詳細については、「 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)」を参照してください。  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]デザイナーで新しい Word 文書を開き、追加、 **EmployeeControls**プロジェクトを**ソリューション エクスプ ローラー**です。  
  
## <a name="adding-content-controls-to-the-document"></a>文書にコンテンツ コントロールを追加する  
 ユーザーが従業員に関する情報を表示または編集できる 3 種類のコンテンツ コントロールが含まれるテーブルを作成します。  
  
#### <a name="to-add-content-controls-to-the-document"></a>文書にコンテンツ コントロールを追加するには  
  
1.  ホストされている Word 文書で、 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 、リボン上のデザイナーを選択して、**挿入** タブ。  
  
2.  **テーブル**グループで、選択**テーブル**、および 2 つの列と 3 つの行を含むテーブルを挿入します。  
  
3.  最初の列に次のようにテキストを入力します。  
  
    ||  
    |-|  
    |**従業員の名前**|  
    |**入社日**|  
    |**タイトル**|  
  
4.  テーブルの 2 番目の列で、最初の行を選択します (横に**Employee Name**)。  
  
5.  リボンで、選択、**開発者**タブです。  
  
    > [!NOTE]  
    >  **[開発]** タブが表示されていない場合は、最初にこれを表示する必要があります。 詳細については、「 [How to: Show the Developer Tab on the Ribbon](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)」を参照してください。  
  
6.  **コントロール**グループで、選択、**テキスト**ボタン![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") を追加する<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>最初のセルにします。  
  
7.  テーブルの 2 番目の列で、2 番目の行を選択します (横に**Hire Date**)。  
  
8.  **コントロール**グループで、選択、**日付選択カレンダー**ボタン![DatePickerContentControl](../vsto/media/datepicker.gif "DatePickerContentControl") を追加するには<xref:Microsoft.Office.Tools.Word.DatePickerContentControl> 2 番目のセルにします。  
  
9. テーブルの 2 番目の列で、3 番目の行を選択します (横に**タイトル**)。  
  
10. **コントロール**グループで、選択、**ドロップ ダウン リスト**ボタン![DropDownListContentControl](../vsto/media/dropdownlist.gif "DropDownListContentControl")を追加するには<xref:Microsoft.Office.Tools.Word.DropDownListContentControl>最後のセルにします。  
  
 これで、このプロジェクトのユーザー インターフェイスが完成しました。 ここでこのプロジェクトを実行すると、最初の行にテキストを入力し、2 つ目の行で日付を選択できます。 次の手順では、表示するデータを XML ファイル内の文書に添付します。  
  
## <a name="creating-the-xml-data-file"></a>XML データ ファイルの作成  
 通常は、ファイルやデータベースなどの外部ソースからカスタム XML 部分に格納する XML 文字列を取得する必要があります。 このチュートリアルでは、文書内のコンテンツ コントロールにバインドする要素でマークされた従業員データを含む、XML ファイルを作成します。 実行時に使用可能にするため、カスタマイズ アセンブリのリソースとして XML ファイルを埋め込みます。  
  
#### <a name="to-create-the-data-file"></a>データ ファイルを作成するには  
  
1.  **[プロジェクト]** メニューの **[新しい項目の追加]**をクリックします。  
  
     **[新しい項目の追加]** ダイアログ ボックスが表示されます。  
  
2.  **テンプレート**ペインで、 **XML ファイル**です。  
  
3.  ファイルの名前を付けます**employees.xml**を選択し、**追加**ボタンをクリックします。  
  
     **Employees.xml**コード エディターでファイルが開きます。  
  
4.  内容を置き換える、 **employees.xml**を次のテキスト ファイルです。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <employees xmlns="http://schemas.microsoft.com/vsto/samples">  
      <employee>  
        <name>Karina Leal</name>  
        <hireDate>1999-04-01</hireDate>  
        <title>Manager</title>  
      </employee>  
    </employees>  
    ```  
  
5.  **ソリューション エクスプ ローラー**、選択、 **employees.xml**ファイル。  
  
6.  **プロパティ**ウィンドウで、**ビルド アクション**プロパティに値を変更し、**埋め込まれたリソース**です。  
  
     この操作によって、プロジェクトをビルドしたときに、XML ファイルがリソースとしてアセンブリに埋め込まれます。 これにより、実行時に XML ファイルの内容にアクセスできます。  
  
## <a name="creating-an-xml-schema"></a>XML スキーマを作成する  
 コンテンツ コントロールをカスタム XML 部分の 1 つの要素にバインドする場合は、XML スキーマを使用する必要はありません。 ただし、<xref:Microsoft.Office.Tools.Word.DropDownListContentControl> を複数の値にバインドする場合は、前の手順で作成した XML データ ファイルを検証する XML スキーマを作成する必要があります。 XML スキーマには、`title` 要素に割り当てることができる値を定義します。 このチュートリアルの後半で、この要素に <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> をバインドします。  
  
#### <a name="to-create-an-xml-schema"></a>XML スキーマを作成するには  
  
1.  **[プロジェクト]** メニューの **[新しい項目の追加]**をクリックします。  
  
     **[新しい項目の追加]** ダイアログ ボックスが表示されます。  
  
2.  **テンプレート**ペインで、 **XML スキーマ**です。  
  
3.  スキーマの名前を付けます**employees.xsd**を選択し、**追加**ボタンをクリックします。  
  
     スキーマ デザイナーが開きます。  
  
4.  **ソリューション エクスプ ローラー**、ショートカット メニューを開き、 **employees.xsd**を選択し**コードの表示**です。  
  
5.  内容を置き換える、 **employees.xsd**次のスキーマを持つファイルです。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <xs:schema xmlns="http://schemas.microsoft.com/vsto/samples"   
        targetNamespace="http://schemas.microsoft.com/vsto/samples"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema"  
        elementFormDefault="qualified">  
      <xs:element name="employees" type="EmployeesType"></xs:element>  
      <xs:complexType name="EmployeesType">  
        <xs:all>  
          <xs:element name="employee" type="EmployeeType"/>  
        </xs:all>  
      </xs:complexType>  
      <xs:complexType name="EmployeeType">  
        <xs:sequence>  
          <xs:element name="name" type="xs:string" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="hireDate" type="xs:date" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="title" type="TitleType" minOccurs="1" maxOccurs="1"/>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:simpleType name="TitleType">  
        <xs:restriction base="xs:string">  
          <xs:enumeration value ="Engineer"/>  
          <xs:enumeration value ="Designer"/>  
          <xs:enumeration value ="Manager"/>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:schema>  
    ```  
  
6.  **ファイル** メニューのをクリックして**すべて保存**に変更を保存する、 **employees.xml**と**employees.xsd**ファイル。  
  
## <a name="attaching-the-xml-schema-to-the-document"></a>XML スキーマを文書に添付する  
 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> を `title` 要素の有効な値にバインドするためには、XML スキーマを文書に添付する必要があります。  
  
#### <a name="to-attach-the-xml-schema-to-the-document-includeword15shortvstoincludesword-15-short-mdmd"></a>XML スキーマをドキュメントに添付するには ([!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)])  
  
1.  アクティブ化**EmployeeControls.docx**デザイナーでします。  
  
2.  リボンで、選択、**開発者** タブをクリックして、**アドイン**ボタンをクリックします。  
  
3.  **テンプレートとアドイン** ダイアログ ボックスで、選択、 **XML スキーマ** タブをクリックして、**スキーマの追加**ボタンをクリックします。  
  
4.  参照、 **employees.xsd**スキーマ前に作成した、プロジェクト ディレクトリにあるをクリックして、**開く**ボタンをクリックします。  
  
5.  選択、 **OK**ボタンをクリックして、**スキーマ設定** ダイアログ ボックス。  
  
6.  選択、 **OK**を閉じる ボタン、**テンプレートとアドイン** ダイアログ ボックス。  
  
#### <a name="to-attach-the-xml-schema-to-the-document-word-2010"></a>XML スキーマをドキュメントに添付するには (Word 2010)  
  
1.  アクティブ化**EmployeeControls.docx**デザイナーでします。  
  
2.  リボンで、選択、**開発者**タブです。  
  
3.  **XML**グループで、選択、**スキーマ**ボタンをクリックします。  
  
4.  **テンプレートとアドイン** ダイアログ ボックスで、選択、 **XML スキーマ** タブをクリックして、**スキーマの追加**ボタンをクリックします。  
  
5.  参照、 **employees.xsd**は、プロジェクト ディレクトリに格納しを選択する前に作成したスキーマ、**開く**ボタンをクリックします。  
  
6.  選択、 **OK**ボタンをクリックして、**スキーマ設定** ダイアログ ボックス。  
  
7.  選択、 **OK**を閉じる ボタン、**テンプレートとアドイン** ダイアログ ボックス。  
  
     **XML 構造**作業ウィンドウが表示されます。  
  
8.  閉じる、 **XML 構造**作業ウィンドウ。  
  
## <a name="adding-a-custom-xml-part-to-the-document"></a>カスタム XML 部分を文書に追加する  
 コンテンツ コントロールを XML ファイル内の要素にバインドするためには、XML ファイルの内容を文書内の新しいカスタム XML 部分に追加する必要があります。  
  
#### <a name="to-add-a-custom-xml-part-to-the-document"></a>カスタム XML 部分を文書に追加するには  
  
1.  **ソリューション エクスプ ローラー**、ショートカット メニューを開き、 **ThisDocument.cs**または**ThisDocument.vb**を選択し**コードの表示**です。  
  
2.  `ThisDocument` クラスに次の宣言を追加します。 このコードでは、カスタム XML 部分を文書に追加するために使用する複数のオブジェクトを宣言しています。  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#1)]  
  
3.  `ThisDocument` クラスに次のメソッドを追加します。 このメソッドは、アセンブリにリソースとして埋め込まれている XML データ ファイルの内容を取得し、それを XML 文字列として返します。  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#3)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#3)]  
  
4.  `ThisDocument` クラスに次のメソッドを追加します。 `AddCustomXmlPart` メソッドは、受け取った XML 文字列を含むカスタム XML 部分を作成します。  
  
     カスタム XML 部分が一度だけ作成されるように、このメソッドは、一致する GUID を持つカスタム XML 部分が文書内に存在しない場合のみカスタム XML 部分を作成します。 このメソッドは、初めて呼び出されたときに、<xref:Microsoft.Office.Core._CustomXMLPart.Id%2A> プロパティの値を `employeeXMLPartID` 文字列に格納します。 `employeeXMLPartID` 文字列の値は、<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 属性によって宣言されているため、文書内に保持されます。  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#4)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#4)]  
  
## <a name="binding-the-content-controls-to-elements-in-the-custom-xml-part"></a>コンテンツ コントロールをカスタム XML 部分の要素にバインドする  
 使用してカスタム XML 部分の要素にバインドする各コンテンツ コントロール、 **XMLMapping**各コンテンツ コントロールのプロパティです。  
  
#### <a name="to-bind-the-content-controls-to-elements-in-the-custom-xml-part"></a>コンテンツ コントロールをカスタム XML 部分の要素にバインドするには  
  
1.  `ThisDocument` クラスに次のメソッドを追加します。 このメソッドは、各コンテンツ コントロールをカスタム XML 部分の要素にバインドし、<xref:Microsoft.Office.Tools.Word.DatePickerContentControl> の日付表示形式を設定します。  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#5)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#5)]  
  
## <a name="running-your-code-when-the-document-is-opened"></a>文書が開かれたときにコードを実行する  
 カスタム XML 部分を作成し、文書が開かれたときにカスタム コントロールをデータにバインドします。  
  
#### <a name="to-run-your-code-when-the-document-is-opened"></a>文書が開かれたときにコードを実行するには  
  
1.  `ThisDocument_Startup` クラスの `ThisDocument` メソッドに次のコード行を追加します。 このコードは元の XML 文字列を取得、 **employees.xml**ファイルが、ドキュメント内の新しいカスタム XML 部分に XML 文字列を追加し、コンテンツ コントロールをカスタム XML 部分の要素にバインドします。  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#2)]  
  
## <a name="testing-the-project"></a>プロジェクトのテスト  
 文書を開くと、コンテンツ コントロールにカスタム XML 部分の要素のデータが表示されます。 クリックすることができます、<xref:Microsoft.Office.Tools.Word.DropDownListContentControl>の 3 つの有効な値のいずれかを選択、`title`で定義されている要素、 **employees.xsd**ファイル。 コンテンツ コントロールに表示されたデータを編集すると、新しい値が文書内のカスタム XML 部分に保存されます。  
  
#### <a name="to-test-the-content-controls"></a>コンテンツ コントロールをテストするには  
  
1.  F5 キーを押してプロジェクトを実行します。  
  
2.  文書内に次のようなテーブルが表示されることを確認します。 2 つ目の列の文字列は、文書内のカスタム XML 部分の要素から取得されます。  
  
    |||  
    |-|-|  
    |**従業員の名前**|**Karina Leal**|  
    |**入社日**|**1999 年 4 月 1 日**|  
    |**タイトル**|**マネージャー**|  
  
3.  右側にあるセルを選択して、 **Employee Name**セルし、別の名前を入力します。  
  
4.  右側にあるセルを選択して、 **Hire Date**セルおよび日付選択カレンダーで別の日付を選択します。  
  
5.  右側にあるセルを選択して、**タイトル**セルおよびドロップダウン リストから項目を選択します。  
  
6.  文書を保存して閉じます。  
  
7.  エクスプローラーで、プロジェクトの下にある \bin\Debug フォルダーを開きます。  
  
8.  ショートカット メニューを開き、 **EmployeeControls.docx**を選択し**の名前を変更**です。  
  
9. ファイルの名前を付けます**EmployeeControls.docx.zip**です。  
  
     **EmployeeControls.docx** Open XML 形式のドキュメントを保存します。 この文書の拡張子を .zip に変更すると、文書の内容を確認できます。 Open XML の詳細については、技術記事を参照してください。 [、Office (2007) Open XML ファイル形式の概要](http://msdn.microsoft.com/en-us/96018532-f62c-4da7-bbff-16b96a483fbf)です。  
  
10. 開く、 **EmployeeControls.docx.zip**ファイル。  
  
11. 開く、 **customXml**フォルダーです。  
  
12. ショートカット メニューを開き、 **item2.xml**を選択し**開く**です。  
  
     このファイルには、文書に追加したカスタム XML 部分が含まれています。  
  
13. `name`、`hireDate`、`title` の各要素に文書内のコンテンツ コントロールに入力した値が設定されていることを確認します。  
  
14. 閉じる、 **item2.xml**ファイル。  
  
## <a name="next-steps"></a>次の手順  
 コンテンツ コントロールの使用方法の詳細については、次の各トピックを参照してください。  
  
-   用意されているすべてのコンテンツ コントロールを使用してテンプレートを作成できます。 詳細については、次を参照してください。[チュートリアル: コントロールによるテンプレートを使用してコンテンツを作成する](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)です。  
  
-   文書を閉じた状態でカスタム XML 部分のデータを変更できます。 その文書を次にユーザーが開いたときには、XML 要素にバインドされたコンテンツ コントロールに新しいデータが表示されます。  
  
-   コンテンツ コントロールを使用して文書の一部を保護できます。 詳細については、「 [How to: Protect Parts of Documents by Using Content Controls](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [拡張オブジェクトによる Word の自動化](../vsto/automating-word-by-using-extended-objects.md)   
 [コンテンツ コントロール](../vsto/content-controls.md)   
 [方法: Word 文書にコンテンツ コントロールを追加](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [方法: コンテンツ コントロールを使用してドキュメントを保護する.](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  