---
title: "方法 : 構成を作成および編集する | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solution build configurations, editing
- build configurations, creating
- solution build configurations, creating
- build configurations, editing
- builds [Visual Studio], setting up
- property pages
- Configuration Manager
- project build configurations, creating
- project build configurations, editing
ms.assetid: 19be121c-148e-4ece-bbfc-d20b08cfc3f7
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: afa939c0b8a033930f5e8e7bcc525d6f33e55f86
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-and-edit-configurations"></a>方法 : 構成を作成および編集する
ソリューションに対して、複数のビルド構成を作成することができます。 たとえば、問題を検出して修正するためにテスト担当者が使用できるデバッグ ビルドを構成できます。他にも、多様な顧客に配布できる多様な種類のビルドを構成できます。  

 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  

## <a name="creating-build-configurations"></a>ビルド構成の作成  
 **[構成マネージャー]** ダイアログ ボックスを使用して、既存のビルド構成を選択または変更することも、新しい構成を作成することもできます。  

#### <a name="to-open-the-configuration-manager-dialog-box"></a>[構成マネージャー] ダイアログ ボックスを開くには  

-   **ソリューション エクスプローラー**で、ソリューションのショートカット メニューを開き、**[構成マネージャー]** をクリックします。  

    > [!NOTE]
    >  **[構成マネージャー]** がショートカット メニューに表示されない場合は、メニュー バーの **[ビルド]** メニューを確認してください。 どちらにも表示されていない場合は、メニュー バーで **[ツール]**、**[オプション]** の順にクリックします。**[オプション]** ダイアログ ボックスの左ウィンドウで **[プロジェクトおよびソリューション]**、**[全般]** の順に展開し、右ウィンドウで **[ビルド構成の詳細を表示]** チェック ボックスをオンにします。  

     **[構成マネージャー]** ダイアログ ボックスでは、**[アクティブ ソリューション構成]** ボックスの一覧を使用して、ソリューション全体のビルド構成の選択、既存構成の変更、または新しい構成の作成を行うことができます。 **[アクティブ ソリューション プラットフォーム]** ドロップダウン リストを使用すると、構成の対象となるプラットフォームの選択、既存プラットフォームの変更、または新しいプラットフォームの追加を行うことができます。 **[プロジェクトのコンテキスト]** ウィンドウには、ソリューション内のプロジェクトが表示されます。 各プロジェクトについて、プロジェクト固有の構成とプラットフォームの選択、既存の構成とプラットフォームの変更、または新しい構成の作成あるいは新しいプラットフォームの追加を行うことができます。 また、ソリューション全体の構成を使用してソリューションをビルドまたは配置する際に、各プロジェクトを含めるかどうかをチェック ボックスで指定することができます。  

 必要な構成を設定したら、その構成に適したプロジェクト プロパティを設定できます。  

#### <a name="to-set-properties-based-on-configurations"></a>構成に基づいてプロパティを設定するには  

-   **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、**[プロパティ]** を選択します。  

     **[プロパティ ページ]** ウィンドウが開きます。  

     構成に応じたプロパティを設定できます。 たとえば、リリース構成の場合、ソリューションのビルド時にコードを最適化することを指定できます。デバッグ構成の場合、`DEBUG` 条件付きコンパイル シンボルを含むことを指定できます。 プロパティ ページの設定について詳しくは、「[プロジェクトおよびソリューションのプロパティの管理](../ide/managing-project-and-solution-properties.md)」をご覧ください。  

## <a name="creating-and-modifying-project-configurations"></a>プロジェクト構成の作成と変更  

#### <a name="to-create-a-project-configuration"></a>プロジェクト構成を作成するには  

1.  **[構成マネージャー]** ダイアログ ボックスを開きます。  

2.  **[プロジェクト]** 列でプロジェクトを選択します。  

3.  そのプロジェクトの **[構成]** ボックスの一覧の **[新規作成]** をクリックします。  

     **[新しいプロジェクト構成]** ダイアログ ボックスが表示されます。  

4.  **[名前]** ボックスに、新しい構成の名前を入力します。  

5.  既存のプロジェクト構成に指定されているプロパティ設定を使用するには、**[設定のコピー元]** ボックスの一覧から構成を選択します。  

6.  ソリューション全体の構成を同時に作成するには、**[新しいソリューション構成を作成する]** チェック ボックスをオンにします。  

#### <a name="to-rename-a-project-configuration"></a>プロジェクト構成の名前を変更するには  

1.  **[構成マネージャー]** ダイアログ ボックスを開きます。  

2.  **[プロジェクト]** 列で、プロジェクト構成の名前を変更するプロジェクトを選択します。  

3.  そのプロジェクトの **[構成]** ボックスの一覧の **[編集]** をクリックします。  

     **[プロジェクト構成の編集]** ダイアログ ボックスが表示されます。  

4.  変更するプロジェクト構成名を選択します。  

5.  **[名前変更]** をクリックし、新しい名前を入力します。  

## <a name="creating-and-modifying-solution-wide-build-configurations"></a>ソリューション全体のビルド構成の作成と変更  

#### <a name="to-create-a-solution-wide-build-configuration"></a>ソリューション全体のビルド構成を作成するには  

1.  **[構成マネージャー]** ダイアログ ボックスを開きます。  

2.  **[アクティブ ソリューション構成]** ボックスの一覧で、**[新規作成]** をクリックします。  

     **[新しいソリューション構成名]** ダイアログ ボックスが表示されます。  

3.  **[名前]** ボックスに、新しい構成の名前を入力します。  

4.  既存のソリューション構成に指定されている設定を使用するには、**[設定のコピー元]** ボックスの一覧から構成を選択します。  

5.  プロジェクト構成を同時に作成するには、**[新しいプロジェクト構成を作成する]** チェック ボックスをオンにします。  

#### <a name="to-rename-a-solution-wide-build-configuration"></a>ソリューション規模のビルド構成の名前を変更するには  

1.  **[構成マネージャー]** ダイアログ ボックスを開きます。  

2.  **[アクティブ ソリューション構成]** ボックスで **[編集]** をクリックします。  

     **[ソリューション構成の編集]** ダイアログ ボックスが表示されます。  

3.  変更するソリューション構成名を選択します。  

4.  **[名前変更]** をクリックし、新しい名前を入力します。  

#### <a name="to-modify-a-solution-wide-build-configuration"></a>ソリューション全体のビルド構成を変更するには  

1.  **[構成マネージャー]** ダイアログ ボックスを開きます。  

2.  **[アクティブ ソリューション構成]** ボックスの一覧で、構成を選択します。  

3.  **[プロジェクトのコンテキスト]** ウィンドウで、すべてのプロジェクトに対して、必要な **[構成]** と **[プラットフォーム]** を選択し、**[ビルド]** するかどうかおよび **[配置]** するかどうかを指定します。  

## <a name="see-also"></a>関連項目  
 [ビルド構成について](../ide/understanding-build-configurations.md)   
 [Visual Studio でのプロジェクトとソリューションのビルドおよびクリーン](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [プロジェクトおよびソリューションのプロパティの管理](managing-project-and-solution-properties.md)

