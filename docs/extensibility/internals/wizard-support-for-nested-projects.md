---
title: "ウィザードでサポートされる入れ子になったプロジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7191d31d4ec53fb26f4ab20114201836f1b58fc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="wizard-support-for-nested-projects"></a>ウィザードでサポートされる入れ子になったプロジェクト
IDE は、親プロジェクトの入れ子になったプロジェクトを実装できる 2 つのウィザードを実行します。**新しいプロジェクト**ウィザードと**項目の追加**ウィザード。  
  
 ユーザーが開始した場合、**新しいプロジェクト**を選択してウィザード**プロジェクトの追加**をクリックすると、**新しいプロジェクト**[ファイル] メニューまたは選択して**追加**右クリックして**新しいプロジェクト**IDE でソリューション エクスプ ローラーが実行、 **AddProject**コマンドと、親プロジェクトの実装、 **AddProject**コマンドは、テンプレートは、プロジェクト ファイルまたはコンテキスト パラメーターのセットを持つウィザード (.vsz) ファイルにするかを返します。  
  
 同様に、親プロジェクトの実装の**AddItem**ウィザードには、コンテキスト パラメーターの異なるセットを持つ .vsz ファイルが返されます。  
  
 ウィザードの詳細については、次を参照してください。[ウィザード (です。Vsz) ファイル](../../extensibility/internals/wizard-dot-vsz-file.md)、[コンテキスト パラメーター](../../extensibility/internals/context-parameters.md)と[プロジェクトと項目テンプレートの登録](../../extensibility/internals/registering-project-and-item-templates.md)です。  
  
## <a name="see-also"></a>関連項目  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [入れ子になったプロジェクト](../../extensibility/internals/nesting-projects.md)