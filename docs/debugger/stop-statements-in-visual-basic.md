---
title: "Visual Basic の Stop ステートメント | Microsoft Docs"
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
  - "VB"
helpviewer_keywords: 
  - "ブレークポイント, Stop ステートメント"
  - "デバッグ [Visual Basic], Stop ステートメントとブレークポイント"
  - "デバッグ (マネージ コードの), Stop ステートメントとブレークポイント"
  - "End ステートメント"
  - "Stop ステートメント, Stop ステートメントの概要"
ms.assetid: 4ad3fe5c-3dfb-4913-b2eb-a0b635751c18
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Visual Basic の Stop ステートメント
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ブレークポイントを設定する別の方法として、Visual Basic の Stop ステートメントをプログラムで使用できます。  デバッガーが Stop ステートメントを実行すると、プログラムの実行が中断されます。つまり、中断モードに入ります。  C\# では、System.Diagnostics.Debugger.Break への呼び出しを使用して、プログラムの実行を中断できます。  
  
 ソース コードを編集することで Stop ステートメントを設定または削除できます。  デバッガー コマンドでは、ブレークポイントを設定またはクリアできますが、Stop ステートメントを設定またはクリアすることはできません。  
  
 Stop ステートメントは、End ステートメントとは異なり、変数をリセットしたり、デザイン モードに戻ったりすることはありません。  アプリケーションの実行を継続するには \[デバッグ\] メニューの \[続行\] をクリックします。  
  
 Just\-In\-Time デバッグが有効な場合は、デバッガーの外部で実行中の Visual Basic アプリケーションの Stop ステートメントによって、デバッガーが起動します。  Just\-In\-Time デバッグが有効でない場合、Stop ステートメントは End ステートメントと同様に機能し、実行を終了します。  QueryUnload イベントや Unload イベントが発生しないため、Visual Basic アプリケーションのリリース バージョンに設定されたすべての Stop ステートメントを削除する必要があります。  詳細については、「[Just\-In\-Time デバッグ](../debugger/just-in-time-debugging-in-visual-studio.md)」を参照してください。  
  
 Stop ステートメントを削除しなくて済むようにするには、次のような条件付きコンパイルを使用できます。  
  
```  
#If DEBUG Then  
   Stop  
#Else  
   ' Don't stop  
#End If  
```  
  
 Stop ステートメントの代わりに、Assert ステートメントを使用する方法もあります。  Debug.Assert ステートメントは、指定した条件を満たさない場合にだけ実行を中断し、リリース バージョンのビルド時に自動的に削除されます。  詳細については、「[マネージ コードのアサーション](../debugger/assertions-in-managed-code.md)」を参照してください。  デバッグ バージョンで常に実行を中断する Assert ステートメントが必要な場合は、次のコードを使用します。  
  
```  
Debug.Assert(false)  
```  
  
 また、Debug.Fail メソッドを使用する方法もあります。  
  
```  
Debug.Fail("a clever output string goes here")  
```  
  
## 参照  
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [C\#、F\#、および Visual Basic のプロジェクト](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [マネージ コードのデバッグ](../debugger/debugging-managed-code.md)