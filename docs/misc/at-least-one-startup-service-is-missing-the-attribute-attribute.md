---
title: "At least one startup service is missing the &#39;attribute&#39; attribute | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.projfile_missing_ss_attrib"
ms.assetid: 987c42dc-4394-4b07-b7fa-a8e7afc6fdfb
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# At least one startup service is missing the &#39;attribute&#39; attribute
スタートアップ サービスが ID 属性を必要としていますが、`<Service>` 要素に見つかりませんでした。  次に例を示します。  
  
```  
<Service ID="{0000-0000-0000-00000000-000000000000}"/>  
```  
  
 これは、プロジェクト ファイルが破損していることを示します。  
  
 このエラーの原因として最も可能性が高いのは、プロジェクト ファイルを手動で編集したことです。  
  
 **このエラーを解決するには**  
  
-   プロジェクト ファイルを保存します。  
  
     破損のある箇所は書き出されません。プロジェクトを次に開くときには、このエラーは発生しません。  
  
## 参照  
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ja-jp/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)