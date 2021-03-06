---
title: "方法 : テンプレートの問題を解決する | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio templates, troubleshooting
ms.assetid: 3e577ad2-f725-4c11-93b3-477f2404ec81
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: af00efbeb759bfc41d12e0ab814ecadd4bbc7799
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-troubleshoot-templates"></a>方法 : テンプレートの問題を解決する
テンプレートを開発環境に読み込むことができない場合に、問題を突き止める方法はいくつかあります。  
  
## <a name="validating-the-vstemplate-file"></a>.vstemplate ファイルの検証  
 テンプレートの .vstemplate ファイルが [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] テンプレート スキーマに準拠していないと、テンプレートが **[新しいプロジェクト]** ダイアログ ボックスに表示されないことがあります。  
  
#### <a name="to-validate-the-vstemplate-file"></a>.vstemplate ファイルを検証するには  
  
1.  テンプレートを含む .zip ファイルを探します。  
  
2.  .zip ファイルを展開します。  
  
3.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] の **[ファイル]** メニューの **[開く]** をクリックし、**[ファイル]** をクリックします。  
  
4.  テンプレートの .vstemplate ファイルを選択し、**[開く]** をクリックします。  
  
5.  .vstemplate ファイルの XML が [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] テンプレート スキーマに準拠していることを確認します。 .vstemplate スキーマの詳細については、「[Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)」を参照してください。  
  
    > [!NOTE]
    >  .vstemplate ファイルを作成する際に IntelliSense サポートを取得するには、`xmlns` 属性を `VSTemplate` 要素に追加し、http://schemas.microsoft.com/developer/vstemplate/2005 の値を割り当てます。  
  
6.  .vstemplate ファイルを保存して、閉じます。  
  
7.  テンプレートに含まれるファイルを選択して右クリックし、**[送る]** を選択し、**[圧縮 (zip 形式) フォルダー]** をクリックします。 選択したファイルは .zip ファイルに圧縮されます。  
  
8.  新しい .zip ファイルを古い .zip ファイルと同じディレクトリに配置します。  
  
9. 抽出したテンプレート ファイルと古いテンプレート .zip ファイルを削除します。  
  
## <a name="monitoring-the-event-log"></a>イベント ログの監視  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] は、テンプレート .zip ファイルの処理中に発生したエラーを記録します。 **[新しいプロジェクト]** ダイアログ ボックスに表示されるはずのテンプレートが表示されない場合は、**[イベント ビューアー]** を使用して問題のトラブルシューティングを行うことができます。  
  
#### <a name="to-locate-template-errors-in-event-viewer"></a>イベント ビューアーでテンプレート エラーを見つけるには  
  
1.  Windows で、**[スタート]** をクリックし、**[コントロール パネル]** をクリックします。次に、**[管理ツール]** をダブルクリックし、**[イベント ビューアー]** をダブルクリックします。  
  
2.  左ウィンドウで、**[アプリケーション]** をクリックします。  
  
3.  **[ソース]** の値が [`Visual Studio - VsTemplate`] のイベントを探します。  
  
4.  テンプレート イベントをダブルクリックして、エラーを表示します。  
  
## <a name="see-also"></a>関連項目  
 [テンプレートのカスタマイズ](../ide/customizing-project-and-item-templates.md)   
 [プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)   
 [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)