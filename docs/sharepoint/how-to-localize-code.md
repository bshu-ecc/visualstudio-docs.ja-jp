---
title: "方法: コードのローカライズ |Microsoft ドキュメント"
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
- VB
- CSharp
helpviewer_keywords:
- localizing code [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
ms.assetid: 0e852052-5ad4-4517-81cf-8865ec304441
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7c283f8e2b73fdb4ba44322ca09f8fb436d729ec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-localize-code"></a>方法: コードをローカライズする
  ローカライズされていないコードでは、ハードコーディングされた文字列値が使用されています。 コードの文字列をローカライズするには、それらを <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> の呼び出しに置き換えます。このメソッドは、ローカライズされたリソースを参照します。  
  
## <a name="localizing-code"></a>コードのローカライズ  
  
#### <a name="to-localize-code"></a>コードをローカライズするには  
  
1.  **ソリューション エクスプ ローラー**プロジェクト項目のショートカット メニューを開きを選択し、**追加**、**モジュール**です。  
  
     選択、**リソース ファイル**テンプレート。  
  
    > [!NOTE]  
    >  Deployment Type プロパティを使用できるように、SharePoint プロジェクト項目にリソース ファイルを必ず追加します。 このプロパティは、後で必要になります。  
  
2.  既定の言語のリソース ファイルには、.resx 拡張子が付いた任意の名前を付けます (MyAppResources.resx など)。  
  
3.  ローカライズ言語ごとに手順 1. と 2. を繰り返して、SharePoint プロジェクト項目にそれぞれのリソース ファイルを追加します。  
  
     ローカライズされた各リソース ファイルに対しては、同じ基本名にカルチャ ID を加えた名前を使用します  (ドイツ語の場合は MyAppResources.de-DE.resx など)。  
  
4.  各リソース ファイルを開いて、ローカライズされた文字列を追加します。 各ファイルで同じ文字列 ID を使用します。  
  
5.  値を変更、**展開の種類**するには、各リソース ファイルのプロパティ**AppGlobalResource**サーバーの App_GlobalResources フォルダーに配置するには、各ファイルが発生します。  
  
6.  値を受け入れ、**ビルド アクション**として各ファイルのプロパティ**埋め込まれたリソース**です。  
  
     埋め込みリソースはプロジェクトの DLL にコンパイルされます。  
  
7.  プロジェクトをビルドして、リソースのサテライト DLL を作成します。  
  
8.  **パッケージ デザイナー**、選択、**詳細**タブをクリックし、サテライト アセンブリを追加します。  
  
9. **場所**ボックスで、先頭に付加する場所のパスを DE-DE などカルチャ ID フォルダー\\*プロジェクト項目の名前*。 resources.dll です。  
  
10. ソリューションで System.Web アセンブリがまだ参照されていない場合は System.Web アセンブリへの参照を追加し、<xref:System.Web> に対するディレクティブをコードに追加します。  
  
11. UI テキスト、エラー、メッセージ テキストなど、ユーザーへの表示用にコード内でハードコーディングされている文字列をすべて見つけます。 それらの文字列を、次の構文を使用する <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> メソッドの呼び出しに置き換えます。  
  
    ```  
    HttpContext.GetGlobalResourceObject("Resource File Name", "String ID")  
    ```  
  
12. F5 キーを押してアプリケーションをビルドし、実行します。  
  
13. SharePoint で、表示言語を既定の言語から変更します。  
  
     ローカライズされた文字列がアプリケーションに表示されます。 ローカライズされたリソースを表示するには、リソース ファイルのカルチャに対応する Language Pack が SharePoint サーバーにインストールされている必要があります。  
  
## <a name="see-also"></a>関連項目  
 [SharePoint ソリューションのローカライズ](../sharepoint/localizing-sharepoint-solutions.md)   
 [方法: フィーチャーをローカライズ](../sharepoint/how-to-localize-a-feature.md)   
 [方法: ASPX マークアップのローカライズ](../sharepoint/how-to-localize-aspx-markup.md)   
 [方法: リソース ファイルを追加する](../sharepoint/how-to-add-a-resource-file.md)  
  
  