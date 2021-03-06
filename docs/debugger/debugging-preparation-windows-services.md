---
title: "デバッグの準備: Windows サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Windows services
- Windows Service applications, debugging
ms.assetid: ac0a99f7-ec3d-4a20-b17f-698a817fdcc2
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7cd7fc1a71009262b53878f40a1418cd4167efe5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-preparation-windows-services"></a>デバッグの準備 : Windows サービス
Windows サービスは、Microsoft Windows のバックグラウンドで実行されるプログラムです。 Windows サービスには、Telnet サービスや、コンピューターに表示される時計を更新する Windows タイム サービスなどがあります。 Windows サービスは [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 内から実行できないため、サービス コントロール マネージャーのコンテキストで実行する必要があります。 詳細については、次を参照してください。 [Windows サービスの作成](/dotnet/framework/windows-services/how-to-create-windows-services)、 [Windows サービス アプリケーションのデバッグ](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)、および[Windows サービス アプリケーション](/dotnet/framework/windows-services/index)です。  
  
## <a name="see-also"></a>関連項目  
 [マネージ コードをデバッグする](../debugger/debugging-managed-code.md)   
 [C#、F#、および Visual Basic のプロジェクトの種類](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C# のプロジェクトの設定はデバッグ構成](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic のプロジェクトの設定はデバッグ構成](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [方法 : OnStart メソッドをデバッグする](../debugger/how-to-debug-the-onstart-method.md)