---
title: -Rebuild (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /rebuild switch
- rebuild Devenv switch (/rebuild)
- projects [Visual Studio], rebuilding
- /rebuild Devenv switch
- applications [Visual Studio], rebuilding
ms.assetid: c5a8a4bf-0e2b-46eb-a44a-8aeb29b92c32
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fcabe7b1ce4130eb52369ff9f16900b1979b8582
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="rebuild-devenvexe"></a>/Rebuild (devenv.exe)
指定したソリューション構成を消去してからビルドします。  
  
## <a name="syntax"></a>構文  
  
```  
devenv SolutionName /rebuild SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]  
```  
  
## <a name="arguments"></a>引数  
 `SolnConfigName`  
 必須です。 `SolutionName` で指定されたソリューションのリビルドに使用されるソリューション構成の名前。  
  
 `SolutionName`  
 必須です。 ソリューション ファイルの完全パスと名前。  
  
 /project `ProjName`  
 省略可能です。 ソリューション内のプロジェクト ファイルのパスと名前です。 `SolutionName` フォルダーからプロジェクト ファイルへの相対パス、プロジェクトの表示名、またはプロジェクト ファイルの完全なパスと名前を入力できます。  
  
 /projectconfig `ProjConfigName`  
 省略可能です。 指定した `/project` のリビルド時に使用されるプロジェクトのビルド構成の名前。  
  
## <a name="remarks"></a>コメント  
  
-   このスイッチは、統合開発環境 (IDE) 内の **[ソリューションのリビルド]** メニュー コマンドと同じ機能を実行します。  
  
-   空白を含む文字列を二重引用符で囲みます。  
  
-   エラーを含むクリーンとビルドの概要情報は、**[コマンド]** ウィンドウ、または `/out` スイッチで指定された任意のログ ファイルに表示できます。  
  
## <a name="example"></a>例  
 この例では、`Debug` プロジェクトのビルド構成を使用して、`MySolution` の `Debug` ソリューション構成内でプロジェクト `CSharpWinApp` を消去してリビルドします。  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /rebuild Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>関連項目  
 [Devenv コマンド ライン スイッチ](../../ide/reference/devenv-command-line-switches.md)   
 [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)