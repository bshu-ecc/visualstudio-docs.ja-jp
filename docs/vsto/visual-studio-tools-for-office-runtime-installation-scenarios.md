---
title: "Visual Studio Tools for Office Runtime のインストール シナリオ |Microsoft ドキュメント"
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
helpviewer_keywords: Visual Studio Tools for Office runtime, installation scenarios
ms.assetid: 71f34daf-8163-4a53-a401-9cab6581f30d
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e09d83fefee766ce19c71812bccfa751cc90e27e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-tools-for-office-runtime-installation-scenarios"></a>Visual Studio Tools for Office ランタイムのインストール シナリオ
  Visual Studio 2010 Tools for Office Runtime は、次の 3 つの方法でインストールできます。  
  
-   Visual Studio のインストール時。  
  
-   Microsoft Office のインストール時。  
  
-   Visual Studio 2010 Tools for Office Runtime の再頒布可能パッケージのインストール時。  
  
 インストールされるランタイム コンポーネントは、コンピューターの構成およびインストール シナリオによって異なります。  
  
## <a name="runtime-components-that-are-installed-in-each-installation-scenario"></a>各インストール シナリオでインストールされるランタイム コンポーネント  
 Visual Studio 2010 Tools for Office Runtime には、Office ソリューション ローダー、.NET Framework 3.5 用の Office 拡張機能、および [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降用の Office 拡張機能の 3 つのコンポーネントがあります。 ランタイムをインストールすると、常に Office ソリューション ローダーがインストールされます。 .NET Framework 用の Office 拡張機能のインストールは、コンピューターの構成およびインストール シナリオによって異なります。 最初にランタイムをインストールするときにどちらかの Office 拡張機能をインストールできない場合、後で特定の要件を満たすと、インストールされていない Office 拡張機能がランタイムによって自動的にインストールされます。 このランタイムの機能と呼びます*オンデマンド インストール*です。  
  
 各ランタイム インストールのシナリオで、既定でインストールされるランタイム コンポーネントを次の表に示します。 各シナリオの詳細については、後で説明します。  
  
|ランタイムのインストール シナリオ|Office ソリューション ローダー|.NET Framework 3.5 用の Office 拡張機能|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] の Office 拡張機能|[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] の Office 拡張機能|  
|-----------------------------------|----------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------|  
|[!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] 以降を使用する場合|はい|○ (.NET Framework Version 3.5 がインストール済みの場合)|はい|はい|  
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] を使用する場合|はい|○ (.NET Framework Version 3.5 がインストール済みの場合)|いいえ|いいえ|  
|Office 2010 Service Pack 1 (SP1) 以降を使用する場合|はい|○ (.NET Framework Version 3.5 がインストール済みの場合)|○ ([!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] がインストール済みの場合)|いいえ|  
|ランタイムの再頒布可能パッケージのインストール時|はい|○ (.NET Framework Version 3.5 がインストール済みの場合)|○ ([!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] がインストール済みの場合)|○ ([!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] がインストール済みの場合)|  
  
### <a name="installing-the-runtime-with-visual-studio-or-the-microsoft-office-developer-tools-for-visual-studio"></a>Visual Studio または Microsoft Office Developer Tools for Visual Studio のインストール時のランタイムのインストール  
 Visual Studio の Office Developer Tools をインストールすると、開発用コンピューターに [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] および [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 用の Office 拡張機能が常にインストールされます。 また、.NET Framework 3.5 用の Office 拡張機能は、開発用コンピューターに .NET Framework 3.5 が既に存在している場合にのみインストールされます。 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] をインストールした後で .NET Framework 3.5 をインストールすると、初めて .NET Framework 3.5 を対象とする Office プロジェクトを作成するときに、.NET Framework 3.5 用の Office 拡張機能がランタイムによって自動的にインストールされます。  
  
> [!WARNING]  
>  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] 以降を使用して .NET Framework 3.5 を対象とする Office プロジェクトを作成することはできません。  
  
 Office developer tools をインストールする方法の詳細については、次を参照してください。[する方法: Office ソリューションの開発にコンピューターを構成する](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)です。  
  
### <a name="installing-the-runtime-with-office"></a>Office でのランタイムのインストール  
 コンピューターに .NET Framework 3.5 が既に存在している場合、Office をインストールすると、.NET Framework 3.5 用の Office 拡張機能がインストールされます。 Office の後で .NET Framework 3.5 をインストールすると、初めて Office アプリケーションが .NET Framework 3.5 を対象とするソリューションを読み込むときに、.NET Framework 3.5 用の Office 拡張機能がランタイムによって自動的にインストールされます。  
  
 Office のインストール時に [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降が既に存在している場合でも、[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降用の Office 拡張機能は Office と共にインストールされません。  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 用の Office 拡張機能は、Office と共にインストールされます。 エンド ユーザーは、Windows Update をインストールすることで [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] 用の Office 拡張機能を取得できます。  
  
 アプリケーションを使用するために必要な拡張機能をユーザーがインストールした状態にするには、ソリューションの必須コンポーネントとして Visual Studio 2010 Tools for Office Runtime の再頒布可能パッケージの最新バージョンを含めます。 前提条件の詳細については、次を参照してください。[展開用の Office ソリューションの必須コンポーネント](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e)です。  
  
### <a name="installing-the-runtime-by-using-the-runtime-redistributable"></a>ランタイムの再頒布可能パッケージを使用したランタイムのインストール  
 ランタイムをインストールするには、Visual Studio 2010 Tools for Office Runtime の再頒布可能パッケージを手動で実行するか、Office ソリューションの配置時に必須コンポーネントとして再頒布可能パッケージを含めます。  
  
 Visual Studio 2010 Tools for Office Runtime の再頒布可能パッケージを使用してランタイムをインストールするときに、対応するバージョンの .NET Framework がコンピューターに既に存在している場合は、.NET Framework 3.5 用の Office 拡張機能と [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降用の Office 拡張機能がインストールされます。 ランタイムをインストールするときにこれらのバージョンの .NET Framework の 1 つがコンピューターに存在しない場合、その時点では、存在しないバージョンの .NET Framework 用の Office 拡張機能はインストールされません。 存在しないバージョンの .NET Framework を後でインストールすると、次回、対応する Office 拡張機能を必要とするソリューションがインストールされたとき (ClickOnce を使用して配置されたソリューションと共にランタイムがインストールされた場合) または読み込まれたときに (Windows インストーラーを使用して配置されたソリューションと共にランタイムがインストールされた場合)、その拡張機能がランタイムによって自動的にインストールされます。  
  
 ClickOnce ソリューションの必須コンポーネントを含む詳細については、次を参照してください。[する方法: インストールの前提条件エンドユーザーのコンピューターに Office ソリューションを実行する](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98)です。 再頒布可能パッケージからランタイムを手動でインストールする方法の詳細については、次を参照してください。[する方法: Office ランタイム再頒布可能パッケージを Visual Studio Tools をインストール](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio Tools for Office Runtime Overview](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Visual Studio Tools for Office Runtime のアセンブリ](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)  
  
  