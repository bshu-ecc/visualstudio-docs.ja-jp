---
title: "モジュール ビュー - サンプリング データ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Modules view
- sampling profiling method,Modules view
ms.assetid: 816f5633-65d7-41e5-aee1-033628d4e2df
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0cf17377de9a21f52f15b263be07fcacb6966096
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
# <a name="modules-view---sampling-data"></a>モジュール ビュー - サンプリング データ
サンプリング データのモジュール ビューには、プロファイル データでサンプリングされたパフォーマンス データが、モジュールごとにグループ化されて表示されます。 各モジュールが、階層ツリーのルートです。 モジュールのサンプリングされた関数が、モジュール ノードの下に一覧表示されます。  
  
> [!NOTE]
>  Windows 8 および Windows Server 2012 の強化されたセキュリティ機能によって、Visual Studio プロファイラーがこれらのプラットフォームでデータを収集する方法に大幅な変更が必要になりました。 UWP アプリにも新しい収集手法が必要です。 ｢[Performance Tools on Windows 8 and Windows Server 2012 applications](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md) (Windows 8 および Windows Server 2012 アプリケーションのパフォーマンス ツール)」をご覧ください。  
  
 サンプルの収集時に関数が実行されていた場合 (つまり関数が呼び出し履歴の最上位にあった場合) は、実行されていたソース行および命令アドレスが関数ノードの下に一覧表示されます。 データは行や命令の実行時にソース行または命令ポインターについて収集されるため、行データと命令データの両方の包括値と排他値は常に同じです。  
  
|Column|説明|  
|------------|-----------------|  
|**名前**|モジュールの名前、関数、行番号、命令ポインター アドレス。|  
|**プロセス ID**|プロファイリング実行のプロセス ID (PID) です。|  
|**プロセス名**|プロセスの名前です。|  
|**モジュール名**|関数、行、または命令ポインターを含むモジュールの名前。|  
|**モジュール パス**|モジュール、関数、行、または命令ポインターを含むモジュールのパス。|  
|**ソース ファイル**|この関数の定義を含むソース ファイルです。|  
|**関数行番号**|ソース ファイルでのこの関数の開始行番号です。|  
|**包括サンプル数**|-   関数の場合、この関数またはこの関数によって呼び出された関数が実行されたサンプルの数、つまりこの関数を含む呼び出し履歴サンプルの数。<br />-   モジュールの場合、このモジュールの少なくとも 1 つの関数が実行されたサンプルの数。<br />-   行または命令の場合、この行または命令が実行されたサンプルの数。|  
|**包括サンプル %**|-   関数またはモジュールの場合、プロファイリング実行のすべてのサンプルに対する、関数またはモジュールの包括サンプルの割合。<br />-   行または命令の場合、プロファイリング実行のすべてのサンプルに対する、この行または命令が実行されたサンプルの割合。|  
|**排他サンプル数**|-   関数の場合、この関数が直接実行されていた呼び出し履歴サンプルの数、つまり、この関数が呼び出し履歴の最上位にあったときのサンプルの数。<br />-   モジュールの場合、このモジュール内の関数における排他サンプルの合計。<br />-   行または命令の場合、この行または命令が実行されたサンプルの数。|  
|**排他サンプル %**|-   関数またはモジュールの場合、プロファイリング実行のすべてのサンプルに対する、関数またはモジュールの排他サンプルの割合。<br />-   行または命令の場合、プロファイリング実行のすべてのサンプルに対する、この行または命令が実行されたサンプルの割合。|  
  
## <a name="see-also"></a>関連項目  
 [モジュール ビュー - サンプリング](../profiling/modules-view-dotnet-memory-sampling-data.md)   
 [モジュール ビュー - インストルメンテーション](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [モジュール ビュー](../profiling/modules-view-instrumentation-data.md)