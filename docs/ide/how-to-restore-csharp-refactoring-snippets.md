---
redirect_url: /visualstudio/csharp-ide/refactoring-csharp
ms.openlocfilehash: cb4e45847008d99aa17b5ce3dde83da036a53dbb
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
title: "方法 : C# リファクタリング スニペットを復元する | Microsoft Docs" ms.custom: "" ms.date: "11/04/2016" ms.reviewer: "" ms.suite: "" ms.technology: 
  - "vs-ide-general" ms.tgt_pltfrm: "" ms.topic: "article" helpviewer_keywords: 
  - "安全でない展開"
  - "展開、安全でない" ms.assetid: 12114273-7f2f-43d0-abcb-2d4711a3a68d caps.latest.revision: 20 author: "gewarren" ms.author: "gewarren" manager: ghogen
---
# <a name="how-to-restore-c-refactoring-snippets"></a>方法 : C# リファクタリング スニペットを復元する
C# リファクタリング操作は、次のディレクトリにあるコード スニペットに依存しています。  
  
 *インストール ディレクトリ*\Microsoft Visual Studio 15.0\VC#\Snippets\\*言語 ID*\Refactoring  
  
 この Refactoring ディレクトリまたはこのディレクトリ内のファイルを削除または破損すると、IDE では、C# リファクタリング操作が機能しない場合があります。 次の手順は、C# リファクタリング コード スニペットを復元する場合に役立ちます。  
  
### <a name="to-verify-c-refactoring-snippets-are-available-through-the-code-snippet-manager"></a>C# リファクタリング スニペットをコード スニペット マネージャーで使用できることを確認するには  
  
1.  **[ツール]** メニューの **[コード スニペット マネージャー]** を選びます。  
  
2.  **[コード スニペット マネージャー]** ダイアログ ボックスで、**[言語]** ボックスの一覧の **[Visual C#]** を選びます。  
  
     **[リファクタリング]** フォルダーがツリー ビューのフォルダーの一覧に表示されます。  
  
### <a name="to-restore-refactoring-see-comment-in-code-snippet-manager"></a>コード スニペット マネージャーでリファクタリングの see コメントを復元するには  
  
1.  コード スニペット マネージャーのツリー ビューのフォルダーの一覧に **[リファクタリング]** フォルダーが表示されない場合は、次の手順を使って、リファクタリング スニペットをコード スニペット マネージャーに追加します。  
  
2.  **[ツール]** メニューの **[コード スニペット マネージャー]** を選びます。  
  
3.  **[コード スニペット マネージャー]** ダイアログ ボックスで、**[言語]** ボックスの一覧の **[Visual C#]** を選びます。  
  
4.  **[追加]**をクリックします。 **[コード スニペット ディレクトリ]** ダイアログ ボックスが表示されます。このダイアログ ボックスを使って、コード スニペット マネージャーに追加するディレクトリを検索および指定します。  
  
5.  次のディレクトリ パスにある **Refactoring** フォルダーに移動します。  
  
     *インストール ディレクトリ*\Microsoft Visual Studio 15.0\VC#\Snippets\\*言語 ID*\Refactoring  
  
     既定のインストールでは、実際のパスは次のようになります。  
  
     C:\Program Files\Microsoft Visual Studio 15.0\VC#\Snippets\1033\Refactoring  
  
6.  **[コード スニペット ディレクトリ]** ダイアログ ボックスの **[開く]** をクリックし、コード スニペット マネージャーの **[OK]** をクリックします。  
  
## <a name="see-also"></a>関連項目  
 [Visual C# のコード スニペット](../ide/visual-csharp-code-snippets.md)   
 [リファクタリング (C#)](../csharp-ide/refactoring-csharp.md)   
 [コード スニペット](../ide/code-snippets.md)