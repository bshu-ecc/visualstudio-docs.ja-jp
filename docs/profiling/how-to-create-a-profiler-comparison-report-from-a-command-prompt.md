---
title: "方法: コマンド プロンプトからプロファイラー比較レポートを作成する | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fe95412c11da05d409954762f40c46745b98940
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>方法: コマンド プロンプトからプロファイラー比較レポートを作成する
2 つのプロファイリング データ (.VSP または .VSPS) ファイルのパフォーマンス データを比較する [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] プロファイリング ツール レポートを生成できます。 このレポートでは、プロファイリング セッションを比較し、その違い、パフォーマンスの低下、改善を示します。 レポート内の値は、指定された最初のファイルを基準とし、差分 (変化分) を表します。 この差分は、古い値、基準値と、新しい分析による結果の値との違いを測定して計算されます。 プロファイラーのデータの比較は、コード内の関数、アプリケーション内のモジュール、行、命令ポインター (IP)、および種類に基づいて作成できます。  
  
 比較のカテゴリとフィールドの識別子を一覧表示するには、次のコマンド ラインを入力します。  
  
 **VSPerfReport /querydifftables**  *VspFileName1* *VspFileName2*  
  
 比較レポートを作成するには、次の構文を使用します。  
  
 **VSPerfReport /diff**  `VspFileName1` *VspFileName2* [**/**`Options`]  
  
 次の表のオプションを **VSPerfReport /diff** コマンド ラインに追加できます。  
  
|オプション|説明|  
|------------|-----------------|  
|**DiffThreshold:**[*Value*]|このパーセンテージしきい値を下回る場合、差異を無視します。 また、このしきい値を下回る新しいデータは表示されません。|  
|**DiffTable:** *TableName*|このテーブルを使用してファイルを比較します。 既定では、関数テーブルが使用されます。 **VSPerfReport /querydifftables** の一覧にある識別子を指定します。|  
|**DiffColumn:** *ColumnName*|この列を使用して値を比較します。 既定では、排他サンプルのパーセント列が使用されます。 **VSPerfReport /querydifftables** の一覧にある識別子を指定します。|