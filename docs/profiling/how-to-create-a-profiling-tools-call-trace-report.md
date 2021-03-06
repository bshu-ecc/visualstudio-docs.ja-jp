---
title: "方法: プロファイリング ツールのコール トレース レポートを作成する | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1daf97ee7de7a0deea9b3b1c8a9a17529edfe9b4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-profiling-tools-call-trace-report"></a>方法: プロファイリング ツールのコール トレース レポートを作成する
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイリング ツールの*コール トレース レポート*は、アプリケーションの関数に対する各エントリ ポイントと終了ポイント、および実行中の関数から他の関数に対する各呼び出しのタイミング情報を一覧表示します。 コール トレース レポートをデータのプロファイリングに使用できるのは、インストルメンテーション メソッドで収集された場合だけです。  
  
> [!NOTE]
>  コール トレース レポートを [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] で表示することはできません。 コンマ区切り値 (.csv) ファイルまたは XML ファイルを生成するには、**VSPerfReport** のコマンド ライン ツールを使用する必要があります。 このツールの詳細については、「[VSPerfReport](../profiling/vsperfreport.md)」を参照してください。  
  
### <a name="to-create-a-call-trace-report"></a>コール トレース レポートを作成するには  
  
1.  **[コマンド プロンプト]** ウィンドウを開きます。  
  
2.  コマンド プロンプトに次のコマンドを入力します。  
  
     *ToolsPath* **VSPerfReport** *VSPFile*  **/CallTrace [/Xml]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|プロファイリング ツールのコマンド ライン ツールのパス。 詳細については、「[コマンド ライン ツールへのパスの指定](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)」をご覧ください。|  
    |*VSPFile*|プロファイル データ (.vsp または .vsps) ファイル。 完全パスまたは部分パスで指定できます。|  
    |Xml|XML 形式のレポートを生成します。|  
  
## <a name="see-also"></a>関連項目  
 [方法: ETW (Event Tracing for Windows) データを収集する](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)   
 [プロファイリング ツールの API](../profiling/profiling-tools-apis.md)