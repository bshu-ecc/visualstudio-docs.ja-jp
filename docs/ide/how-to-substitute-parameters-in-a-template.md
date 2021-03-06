---
title: "方法 : テンプレート内のパラメーターを置き換える | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- template parameters, substituting
- Visual Studio templates, using parameters
ms.assetid: a62924a7-4ba0-413d-b606-fdbe1fcf2807
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e6e13e704502443c371021c515c7a9578497f829
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-substitute-parameters-in-a-template"></a>方法 : テンプレート内のパラメーターを置き換える
テンプレートに基づいてファイルを作成するとき、クラス名や名前空間などのテンプレート パラメーターを置き換えることができます。 テンプレート パラメーターの完全な一覧については、「[テンプレート パラメーター](../ide/template-parameters.md)」をご覧ください。  
  
## <a name="procedure"></a>プロシージャ  
 テンプレートに基づいてプロジェクトを作成するときは常に、そのテンプレートのファイル内のパラメーターを置き換えることができます。 この手順では、テンプレートを使用して新しいプロジェクトを作成するとき、名前空間の名前を安全なプロジェクト名に置き換えるテンプレートの作成方法について説明します。  
  
#### <a name="to-use-a-parameter-to-replace-namespace-name-with-the-project-name"></a>パラメーターを使用して名前空間の名前をプロジェクト名に置き換えるには  
  
1.  テンプレートの 1 つ以上のコード ファイルにパラメーターを挿入します。 例:  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
    > [!NOTE]
    >  テンプレート パラメーターは、$*parameter*$ という形式で記述します。  
  
2.  テンプレートの .vstemplate ファイルで、このファイルを含む `ProjectItem` 要素を検索します。  
  
3.  `ProjectItem` 要素の `ReplaceParameters` 属性を `true` に設定します。 例:  
  
    ```  
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>  
    ```  
  
## <a name="see-also"></a>関連項目  
 [プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)   
 [テンプレート パラメーター](../ide/template-parameters.md)   
 [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)   
 [ProjectItem 要素 (Visual Studio 項目テンプレート)](../extensibility/projectitem-element-visual-studio-item-templates.md)