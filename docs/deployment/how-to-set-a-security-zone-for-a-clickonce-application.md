---
title: "方法: ClickOnce アプリケーションのセキュリティ ゾーンを設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, security settings
- code access security, ClickOnce applications
- security zones, ClickOnce applications
ms.assetid: d3dac454-518a-44d7-a76e-ccb7b9c3a150
caps.latest.revision: "18"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 2bba62850791f637e93d6c82ff2186ffc5f09652
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>方法 : ClickOnce アプリケーションのセキュリティ ゾーンを設定する
ClickOnce アプリケーションのコード アクセス セキュリティ アクセス許可を設定するときは、まず、 **プロジェクト デザイナー** の **[セキュリティ]**ページで、アクセス許可の基本セットを指定する必要があります。  
  
 また、ほとんどの場合、制限されたアクセス許可セットを含む **[インターネット]** ゾーン、またはより大きいアクセス許可セットを含む **[ローカル イントラネット]** ゾーンを選択することもできます。 アプリケーションにカスタムのアクセス許可が必要な場合は、 **[カスタム]** セキュリティ ゾーンを選択します。 カスタム アクセス許可の設定の詳細については、「 [How to: Set Custom Permissions for a ClickOnce Application](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)」を参照してください。  
  
### <a name="to-set-a-security-zone"></a>セキュリティ ゾーンを設定するには  
  
1.  **ソリューション エクスプ ローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]**をクリックします。  
  
2.  **[セキュリティ]** タブをクリックします。  
  
3.  **[ClickOnce セキュリティ設定を有効にする]** チェック ボックスをオンにします。  
  
4.  **[これは部分的に信頼するアプリケーションです]** オプション ボタンを選択します。  
  
     **[ClickOnce セキュリティのアクセス許可]** セクション内のコントロールが有効になります。  
  
5.  **[アプリケーションのインストール元のゾーン]** ドロップダウン リストでセキュリティ ゾーンを選択します。  
  
## <a name="see-also"></a>関連項目  
 [How to: Set Custom Permissions for a ClickOnce Application](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [ClickOnce アプリケーションのセキュリティ](../deployment/securing-clickonce-applications.md)   
 [ClickOnce アプリケーション用のコード アクセス セキュリティ](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce アプリケーションのセキュリティ](../deployment/securing-clickonce-applications.md)