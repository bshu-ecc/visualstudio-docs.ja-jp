---
title: "CLS 準拠の警告 CLS09806 | Microsoft Docs"
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
  - "CLS09806"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS09806"
ms.assetid: fc97cf0e-c72e-4c09-96be-f90f9840e76e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 準拠の警告 CLS09806
ジェネリック メソッドが CLS 準拠ではありません  
  
 ジェネリック メソッドが CLS 準拠ではありません。  
  
 共通言語サブセット \(CLS\) 準拠の確認の詳細については、「[CLS 準拠のアセンブリ](http://msdn.microsoft.com/ja-jp/3320b57e-ea55-4697-a17d-f509a36a3c93)」を参照してください。  
  
 次の例では CLS09806 が生成されます。  
  
```  
// CLS09806.cpp // compile with: /clr /LD /link /noentry // CLS09806 expected using namespace System::Reflection; [assembly:AssemblyKeyFile("clscompliance.snk")]; using namespace System; [assembly:CLSCompliant (true)]; generic <class T> public ref struct One { public: generic <class U> void Method1() {} };  
```