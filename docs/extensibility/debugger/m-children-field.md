---
title: "m_children フィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9e6c7db4e05873ca0272da4eb551418d466ddc03
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="mchildren-field"></a>m_children フィールド
このタスクに登録されている子タスクの一覧。  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **アセンブリ:** (mscorlib.dll) の mscorlib  
  
 .NET Framework からこの内部のメンバーにアクセスすることはできません、ため、次の構文は共通中間言語 (CIL) に提供されます。  
  
## <a name="syntax"></a>構文  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>コメント  
 タスクの実行中にタスクを実行するスレッドのみはこの配列にアクセスする必要があります。  
  
 タスクが完了した場合、他のスレッドには何も追加または、これからすべてを削除するしないでくださいがない限りこのフィールドにアクセスすることができます。  
  
## <a name="see-also"></a>関連項目  
 [ContingentProperties クラス](../../extensibility/debugger/contingentproperties-class-internal-members.md)