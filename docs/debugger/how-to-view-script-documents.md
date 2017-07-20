---
title: "方法 : スクリプト ドキュメントを表示する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "[スクリプト エクスプローラー]"
ms.assetid: 8b621e53-4508-4b4a-9995-70995b0b9ac8
caps.latest.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 22
---
# 方法 : スクリプト ドキュメントを表示する
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] の以前のバージョンでは、サーバー側スクリプトによって生成されたクライアント側スクリプト ファイルは \[スクリプト エクスプローラー\] ウィンドウに表示されました。  \[スクリプト エクスプローラー\] ウィンドウは非表示のことが多く、クライアント側スクリプトが利用できるかどうかが常に明確とは限りませんでした。  
  
 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] では、サーバー側スクリプトによって生成されたクライアント側スクリプト ファイルは、既定で表示されるソリューション エクスプローラーに表示されます。  \[スクリプト エクスプローラー\] ウィンドウは削除されました。  
  
 クライアント側スクリプト ファイルは、デバッグ モードまたは中断モードのときにのみ表示されます。  これらは **\[スクリプト ドキュメント\]** ノードに表示されます。  
  
 サーバー側スクリプト ファイルは常に表示されます。  これらは **\[\<Web サイトのパス名\>\]** ノードに表示されます。  ノード名は、`c:\...\Website2\` のようになります。  
  
### サーバー側スクリプト ドキュメントを表示するには  
  
1.  **ソリューション エクスプローラー**で、**\[\<Web サイトのパス名\>\]** ノードを開きます。  
  
2.  表示するスクリプト ファイルをダブルクリックします。  
  
     サーバー側スクリプト ファイルがソース ウィンドウに表示されます。  
  
### クライアント側スクリプト ドキュメントを表示するには  
  
1.  **ソリューション エクスプローラー**で、**\[スクリプト ドキュメント\]** ノードを開きます。  
  
2.  表示するスクリプト ファイルをダブルクリックします。  
  
     クライアント側スクリプト ファイルがソース ウィンドウに表示されます。  
  
## 参照  
 [デバッガーでのデータ表示](../debugger/viewing-data-in-the-debugger.md)