---
title: "行ビュー | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.lines
helpviewer_keywords:
- profiling tools reports, Line view
- profiling tools, Line view
- Lines view
ms.assetid: 71ec0781-6031-4e17-af09-f50226018437
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa6492447650be1b7ab9db1725b7146fa808ecc9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="lines-view"></a>行ビュー
行ビューは、サンプリング メソッドを使用して収集したプロファイラー データに対してのみ使用できます。 このビューは、インストルメンテーションを使用して収集したデータに対しては使用できません。  
  
 サンプリング プロファイル データの場合、行ビューにサンプル収集時に直接実行された関数のステートメントが示されます。 .NET メモリ データの場合、行ビューにメモリを割り当てるステートメントが示されます。  
  
 ソース ファイルでは、1 つのステートメントを複数の行にわたって記述することも、複数のステートメントを 1 つの行に含めることもできます。  
  
 ステートメントは、次の項目によって識別されます。  
  
-   function ステートメントを含むソース ファイル。  
  
-   ステートメントを含む関数。  
  
-   ステートメントが開始されるソース行。  
  
-   ステートメントが開始されるソース行の文字。  
  
-   ステートメントが終了するソース行。  
  
-   ステートメントが終了するソース行の文字。  
  
## <a name="see-also"></a>関連項目  
 [行ビュー](../profiling/lines-view-sampling-data.md)   
 [行ビュー - サンプリング](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [行ビュー](../profiling/lines-view-contention-data.md)