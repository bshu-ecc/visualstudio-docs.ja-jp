---
title: "アプリケーションのグローバライズとローカライズ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- globalization [Visual Studio]
- Visual Basic code, international applications
- Visual C#, international applications
- localization [Visual Studio]
- world-ready applications
- international applications [Visual Studio]
ms.assetid: 4d9815ae-3e80-4b4d-933d-f8309aee18d5
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f6e32c592894b5d44a2d257d183c11da01c90456
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="globalizing-and-localizing-applications"></a>アプリケーションのグローバライズとローカライズ
アプリケーションを各国のユーザー向けに配布する場合は、デザイン段階や開発段階で留意する必要のある事項がいくつかあります。 アプリケーションを国際対応にする計画がない場合でも、事前に多少の配慮をしておくと、アプリケーションの将来のバージョンで計画が変更になったときに役立ちます。 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] に組み込まれたサービスを利用すると、Visual Studio でマネージ開発を使用して、異なるロケールに適応できる単一のアプリケーションを簡単に開発できます。  
  
 Visual Studio は、設計の初期段階から、[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] に組み込まれたサービスを活用して各国用アプリケーションを簡単に開発できるようにすることを目指してきました。 次に示す各ページでは、Visual Studio に組み込まれた国際化機能について紹介します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [.NET Framework ベースの国際対応アプリケーションの概要](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)  
 Visual Studio および [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] を使用した国際市場向けソフトウェアの開発に関するいくつかの概念を紹介します。  
  
 [アプリケーションのローカライズ](../ide/localizing-applications.md)  
 特定のカルチャを対象としたアプリケーションのカスタマイズに関するページへのリンクを提供します。  
  
 [アプリケーションのグローバル化](../ide/globalizing-applications.md)  
 複数のカルチャをサポートするアプリケーションの作成について説明するページへのリンクを提供します。  
  
## <a name="related-sections"></a>関連項目  
 [アプリのグローバル化 (HTML)](http://go.microsoft.com/fwlink/?LinkId=258266)  
 HTML を使用してビルドされた Windows 8.1 アプリのグローバル化およびローカライズに役立つ方法トピックとガイドラインが含まれています。  
  
 [アプリのグローバル化 (XAML)](http://go.microsoft.com/fwlink/?LinkId=258267)  
 XAML を使用してビルドされた Windows 8.1 アプリのグローバル化およびローカライズに役立つ方法トピックとガイドラインが含まれています。  
  
 [推奨される国際対応アプリケーション開発手順](http://msdn.microsoft.com/Library/f08169c7-aad8-4ec3-9a21-9ebd3b89986c)  
 国際対応アプリケーションのプログラミングについての背景情報を提供します。  
  
 [クラス ライブラリの概要](/dotnet/standard/class-library-overview)  
 開発プロセスを高速化および最適化し、システム機能へのアクセスを提供する、クラス、インターフェイス、および値型について説明します。  
  
 <xref:System.Globalization>  
 System.Globalization 名前空間内のクラスを示します。これらのクラスは、言語、国/地域、使用するカレンダー、日付形式、通貨と数値、文字列の並べ替え順などのカルチャ情報を定義します。  
  
 <xref:System.Resources>  
 System.Resources 名前空間内のクラスとインターフェイスを示します。開発者は、これらのクラスやインターフェイスを使用して、アプリケーションで使用されるカルチャ固有の各種リソースを作成、保管、および管理できます。