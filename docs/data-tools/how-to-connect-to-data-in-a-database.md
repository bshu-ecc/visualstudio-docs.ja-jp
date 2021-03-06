---
title: "方法 : データベース内のデータに接続する | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "データ [Visual Studio], 接続 (データベースに)"
  - "データ ソース, 作成"
  - "データ ソース, データベース"
  - "データベース接続"
  - "データベース, 接続"
ms.assetid: 6c56e54e-8834-4297-85aa-cc1a443ba556
caps.latest.revision: 55
caps.handback.revision: 55
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 方法 : データベース内のデータに接続する
Visual Studio を使用して、アプリケーションをデータベースに接続できます。  データ接続を作成すると、Visual Studio により、アプリケーションでデータベース内のデータと対話するために使用できるデータ モデルが生成されます。  データ モデルのオブジェクトは、[ウィンドウ](../Topic/Data%20Sources%20Window.md)に表示されます。  その後、**\[データ ソース\]** ウィンドウからデザイン サーフェイスに項目をドラッグすることにより、データ バインディング コントロールを作成できます。  詳細については、「[Visual Studio でのデータへのコントロールのバインド](../data-tools/bind-controls-to-data-in-visual-studio.md)」を参照してください。  
  
 ここでは、データベースに接続する方法と、次の種類のデータ モデルを作成する方法について説明します。  
  
-   データセット  
  
-   Entity Data Model \(EDM\)  
  
> [!NOTE]
>  また、Visual Studio を使用して、データベースから LINQ to SQL クラスを作成することもできます。  ただし、LINQ to SQL クラスは **\[データ ソース\]** ウィンドウに表示されないため、デザイナーに直接ドラッグしてデータ バインディング コントロールを作成することはできません。  データベースから LINQ to SQL クラスを作成する方法の詳細については、「[How to: Create LINQ to SQL Classes Mapped to Tables and Views \(O\/R Designer\)](../Topic/How%20to:%20Create%20LINQ%20to%20SQL%20classes%20mapped%20to%20tables%20and%20views%20\(O-R%20Designer\).md)」を参照してください。  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
##  <a name="dataset"></a> データベースへの接続とデータセットの作成  
 データベースに基づくデータセットを作成すると、Visual Studio により、データのプログラミング可能なビューを表す一連のクラスが作成されます。  メイン クラスは、*型指定されたデータセット*と呼ばれます。  型指定されたデータセットは、データベースのテーブルを表すデータ テーブル オブジェクトを含みます。  型指定されたデータセットの詳細については、「[Visual Studio でのデータセットの操作](../data-tools/dataset-tools-in-visual-studio.md)」を参照してください。  
  
 データセットを作成したら、\[データ ソース\] ウィンドウから WPF デザイナーまたは Windows フォーム デザイナーにデータセット オブジェクトをドラッグすることにより、データ バインディング WPF コントロールまたはデータ バインディング Windows フォーム コントロールを作成できます。  
  
#### アプリケーションをデータベースに接続してデータセットを作成するには  
  
1.  Visual Studio で既存のプロジェクトを開くか、新しいプロジェクトを作成します。  
  
2.  **\[データ\]** メニューの **\[新しいデータ ソースの追加\]** をクリックします。  
  
     **データ ソース構成**ウィザードが開きます。  
  
3.  **\[データソースの種類を選択\]** ページで、**\[データベース\]** を選択し、**\[次へ\]** をクリックします。  
  
4.  **\[データベース モデルの選択\]** ページで、**\[データセット\]** を選択し、**\[次へ\]** をクリックします。  
  
5.  **\[データ接続の選択\]** ページで、利用できる接続の一覧からデータ接続を選択し、**\[次へ\]** をクリックします。  
  
     目的のデータ接続が利用できない場合は、「[新しいデータベース接続の作成](#CreatingDataConnection)」の手順に従って新しい接続を作成します。  
  
6.  **\[接続文字列をアプリケーション構成ファイルに保存する\]** ページで、コンパイルしたアプリケーションに接続文字列を直接保存する場合は、オプションで **\[次の名前で接続を保存する\]** チェック ボックスをオフにします。  既定では、接続がアプリケーション構成ファイルに保存されます。  詳細については、「[方法: 接続文字列を保存および編集する](../Topic/How%20to:%20Save%20and%20Edit%20Connection%20Strings.md)」を参照してください。  
  
7.  **\[データベース オブジェクトの選択\]** ページで、アプリケーションで使用するデータベース オブジェクトを選択します。  また、既定の**データセット名**を置き換えることもできます。  
  
8.  **\[完了\]** をクリックします。  作成したデータセットが **\[データ ソース\]** ウィンドウで利用できるようになります。  
  
    > [!NOTE]
    >  **\[データ ソース\]** ウィンドウが開いていない場合は、**\[データ\]** メニューの **\[データ ソースの表示\]** をクリックしてウィンドウを開きます。  
  
9. これで、**\[データ ソース\]** ウィンドウから WPF デザイナー、Windows フォーム デザイナー、または[Component Designer](../Topic/Component%20Designer.md)に項目をドラッグしてデータ バインディング コントロールを作成できます。  詳細については、「[Visual Studio でのデータへのコントロールのバインド](../data-tools/bind-controls-to-data-in-visual-studio.md)」を参照してください。  
  
##  <a name="edm"></a> データベースへの接続と Entity Data Model の作成  
 データベースに基づく Entity Data Model を作成すると、Visual Studio により、データのプログラミング可能なビューを表す一連のクラスが作成されます。  Entity Data Model および ADO.NET Entity Framework の詳細については、「[エンティティ フレームワークの概要](../Topic/Entity%20Framework%20Overview.md)」を参照してください。  
  
 Entity Data Model を作成したら、\[データ ソース\] ウィンドウから WPF デザイナーにエンティティ オブジェクトをドラッグすることにより、データ バインディング WPF コントロールを作成できます。  
  
#### アプリケーションをデータベースに接続して Entity Data Model を作成するには  
  
1.  Visual Studio で既存のプロジェクトを開くか、新しいプロジェクトを作成します。  
  
2.  **Entity Data Model ウィザード**の手順に従ってデータベースに接続し、モデルの内容を指定します。  詳細については、「[How to: Create a New .edmx File](http://msdn.microsoft.com/ja-jp/beb8189e-e51c-4051-839c-9902c224abf2)」を参照してください。  
  
3.  **Entity Data Model ウィザード**を終了すると、作成した Entity Data Model が Entity Data Model デザイナーで表示され、データ オブジェクトが **\[データ ソース\]** ウィンドウに表示されます。  
  
    > [!NOTE]
    >  **\[データ ソース\]** ウィンドウが開いていない場合は、**\[データ\]** メニューの **\[データ ソースの表示\]** をクリックしてウィンドウを開きます。  
  
4.  WPF デザイナーが開いている場合、**\[データ ソース\]** ウィンドウからデザイナーに項目をドラッグして、Entity Data Model にバインドされたコントロールを作成できます。  詳細については、「[方法: Visual Studio でデータに WPF コントロールをバインドする](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)」を参照してください。  
  
     Windows フォーム デザイナーが開いている場合、**\[データ ソース\]** からデザイナーに項目をドラッグすることはできません。  Entity Data Model にバインドされたコントロールを作成するには、プロジェクトをビルドし、Entity Data Model に基づく新しいオブジェクト データ ソースを追加し、それらのオブジェクトをデザイナーにドラッグする必要があります。  
  
##  <a name="CreatingDataConnection"></a> 新しいデータベース接続の作成  
 **データ ソース構成ウィザード**または **Entity Data Model ウィザード**を使用する場合、使用するデータベースへの接続を指定する必要があります。  データベースへの接続がまだない場合は、次の手順を実行して接続を作成します。  
  
 この説明は、**データ ソース構成ウィザード**または **Entity Data Model ウィザード**を「[データベースへの接続とデータセットの作成](#dataset)」および「[データベースへの接続と Entity Data Model の作成](#edm)」の説明に従って既に開始していることを前提としています。  
  
#### 新しいデータベース接続を作成するには  
  
1.  **データ ソース構成ウィザード**または **Entity Data Model ウィザード**の **\[データ接続の選択\]** ページで、**\[新しい接続\]** をクリックします。  
  
     次のいずれかのアクションが実行されます。  
  
    -   既に Visual Studio でデータ接続を作成している場合、**\[接続の追加\]** ダイアログ ボックスが表示されます。  
  
    -   Visual Studio でデータ接続を初めて作成する場合、**\[データ ソースの選択\]** ダイアログ ボックスが表示されます。  接続先のデータベースの種類を選択し、**\[OK\]** をクリックして **\[接続の追加\]** ダイアログ ボックスを表示します。  
  
2.  **\[接続の追加\]** ダイアログ ボックスに、要求された情報を入力します。  **\[接続の追加\]** ダイアログ ボックスは、データ プロバイダーの種類によって異なります。  
  
    > [!NOTE]
    >  **\[接続の追加\]** ダイアログ ボックスで選択した**データ ソース**が接続先のデータ ソースではない場合、**\[変更\]** をクリックして **\[データ ソースの変更\]** ダイアログ ボックスを開き、別のデータ ソースを選択します。  
  
3.  **\[接続の追加\]** ダイアログ ボックスで、**\[OK\]** をクリックします。  
  
     **データ ソース構成ウィザード**または **Entity Data Model ウィザード**の **\[データ接続の選択\]** ページに戻ります。  
  
4.  **\[データ接続の選択\]** ページで、新しいデータ接続が選択されていることを確認し、**\[次へ\]** をクリックします。  
  
5.  **データ ソース構成ウィザード**または **Entity Data Model ウィザード**の残りの手順を完了します。  
  
## .NET Framework セキュリティ  
 機密情報 \(パスワードなど\) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。  データベースへのアクセスを制御する方法としては、Windows 認証 \(統合セキュリティとも呼ばれます\) を使用する方が安全です。  詳細については、「[接続情報の保護](../Topic/Protecting%20Connection%20Information.md)」を参照してください。  
  
## 参照  
 [データ ソースの概要](../data-tools/add-new-data-sources.md)   
 [データに関するチュートリアル](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio でのデータへの接続](../data-tools/connecting-to-data-in-visual-studio.md)   
 [データ ソースへの接続](../Topic/Connecting%20to%20a%20Data%20Source%20in%20ADO.NET.md)