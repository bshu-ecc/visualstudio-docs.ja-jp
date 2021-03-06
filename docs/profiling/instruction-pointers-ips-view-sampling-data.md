---
title: "命令ポインター (IP) ビュー - サンプリング データ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Instruction Pointers view
ms.assetid: c7f647bb-c5a3-4708-9f9d-33c0fd6e2e96
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b328a12e2b82f6aa688180d9ac57066552e808c9
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
# <a name="instruction-pointers-ips-view---sampling-data"></a>命令ポインター (IP) ビュー - サンプリング データ
サンプリング データの IP ビューには、プロファイルを実行してサンプルを収集したときに直接実行したアセンブリ命令のパフォーマンス データが一覧表示されます。  
  
> [!NOTE]
>  Windows 8 および Windows Server 2012 の強化されたセキュリティ機能によって、Visual Studio プロファイラーがこれらのプラットフォームでデータを収集する方法に大幅な変更が必要になりました。 UWP アプリにも新しい収集手法が必要です。 ｢[Performance Tools on Windows 8 and Windows Server 2012 applications](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md) (Windows 8 および Windows Server 2012 アプリケーションのパフォーマンス ツール)」をご覧ください。  
  
|列|説明|  
|------------|-----------------|  
|**プロセス ID**|プロファイリング実行のプロセス ID (PID) です。|  
|**プロセス名**|プロセスの名前です。|  
|**モジュール名**|命令を含むモジュールの名前。|  
|**モジュール パス**|命令を含むモジュールのパスです。|  
|**ソース ファイル**|命令を含むソース ファイルです。|  
|**関数名**|命令を含む関数の名前です。|  
|**関数行番号**|ソース ファイルでのこの関数の開始行番号です。|  
|**関数アドレス**|読み込まれたバイナリ内の関数の開始メモリ アドレス。|  
|**ソース開始行**|このサンプルが収集されたソース ファイル内の開始行番号です。|  
|**ソース終了行**|このサンプルが収集されたソース ファイル内の終了行番号です。|  
|**ソース開始文字番号**|このサンプルが収集されたソース ファイル行内の開始文字のオフセットです。|  
|**ソース終了文字番号**|このサンプルが収集されたソース ファイル行内の終了文字のオフセットです。|  
|**命令ポインター アドレス**|読み込まれたバイナリ内の命令のアドレスです。|  
|**サンプル数 (関数のみ)**|命令を実行していたときに収集されたサンプルの合計数です。|  
|**サンプル % (関数のみ)**|命令を実行していたときに収集された、プロファイル実行内のすべてのサンプルの割合です。|  
  
## <a name="see-also"></a>関連項目  
 [命令ポインター (IP) ビュー - サンプリング](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)