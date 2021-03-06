---
title: Mark | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d72cef3-bb09-4bbb-8864-6ea0ab623ff9
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6992254d9c62c3f8e35d20a56bd7edd32315f10a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="mark"></a>Mark
VSPerfCmd.exe の **Mark** オプションは、プロファイル データ ファイルに指定した情報を挿入します。 マークは個別の VSPerfReport レポートまたはプロファイラー UI のマーク レポート ビューに一覧表示できます。 **Mark** を使用して、レポートおよびビュー フィルターの開始点と終了点を指定できます。  
  
 コマンド ラインで指定するオプションは **Mark** オプションのみにする必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
VSPerfCmd.exe /Mark:MarkID,[MarkName]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `MarkID`  
 プロファイラー ビューおよびレポートにマーク ID として一覧表示される、ユーザー定義の整数。 `MarkID` は一意である必要はありません。  
  
 `MarkName`  
 (省略可能) プロファイラー ビューおよびレポートにマーク名として一覧表示される、ユーザー定義の文字列。 `MarkName` が指定されていない場合、マーク一覧のマーク名フィールドは空になります。 スペースやスラッシュ ("/") を含む文字列は引用符で囲みます。  
  
## <a name="example"></a>例  
 この例では、ID が 123 でマーク名が "TestMark" というマークを挿入します。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
VSPerfCmd.exe /Mark:123,TestMark  
```  
  
## <a name="see-also"></a>関連項目  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [プロファイリング (サービスの)](../profiling/command-line-profiling-of-services.md)