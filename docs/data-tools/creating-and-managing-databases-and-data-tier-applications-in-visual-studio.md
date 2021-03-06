---
title: "データベース プロジェクト、サーバー プロジェクト、および Visual Studio で DAC プロジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing change, databases
- database features of Visual Studio, managing change
- databases, managing change
- managing change, database servers
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 7f538c51bd5f15f91dfae0d13a9dae8cf4f8afb1
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
---
# <a name="database-projects-and-data-tier-applications-in-visual-studio"></a>データベース プロジェクトと Visual Studio でのデータ層アプリケーション  
データベース プロジェクトを使用するには、新しいデータベースを作成する新しいデータ層アプリケーション (Dac) と既存のデータベースとデータ層アプリケーションを更新します。 データベース プロジェクトと DAC プロジェクトの両方と同じようマネージ コードまたはネイティブ コードには、これらの方法を適用することで、データベース開発作業をバージョン コントロールおよびプロジェクトの管理手法を適用することを有効にします。 開発チームを作成してデータベースとデータベース サーバーに変更を管理することができます、 *DAC プロジェクト*、*データベース プロジェクト*、または*サーバー プロジェクト*およびそのバージョン管理します。 チームのメンバーがファイルをチェック アウトを作成、ビルド、およびで変更をテストする*分離開発環境*、またはチームと共有する前に、サンド ボックス。 コード品質を確保するためには、チームが完了し、実稼働環境に変更を配置する前に、ステージング環境で、データベースの特定のリリースのすべての変更をテストできます。  
  
データ層アプリケーションでサポートされているデータベース機能の一覧は、次を参照してください。[データ層アプリケーションでサポートする機能](http://go.microsoft.com/fwlink/?LinkId=164239)、Microsoft web サイトにします。 データ層アプリケーションでサポートされていない、データベース内の機能を使用する場合は、データベースに変更を管理するデータベース プロジェクトを代わりに使用する必要があります。  
  
## <a name="common-high-level-tasks"></a>一般的な高度なタスク  
  
|高レベルのタスク|関連する参照先|  
|----------------------|------------------------|  
|**データ層アプリケーションの開発の開始:** DAC がで導入された新しい概念[!INCLUDE[sskatmai_r2](../data-tools/includes/sskatmai_r2_md.md)]の定義を含む、[!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]インスタンス クライアント サーバーまたは 3 層で使用されるオブジェクトのデータベースとサポートアプリケーション。 DAC には、テーブルやビューなど、ログインなどのエンティティのインスタンスと共に、データベース オブジェクトが含まれています。 使用することができます[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]DAC プロジェクトを作成するには DAC パッケージ ファイルをビルドしのインスタンスへの配置のデータベース管理者にその DAC パッケージ ファイルを送信、[!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]データベース エンジン。|-   [データ層アプリケーションの作成および管理する](http://go.microsoft.com/fwlink/?LinkId=160741)(Microsoft web サイト)<br />-   [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=227328)|  
|**反復的なデータベース開発を実行する:**チェック アウト、プロジェクトの一部を分離開発環境で更新するようにする場合は、開発者やテスターは、します。 このような環境を使用すると、チームの他のメンバーの影響を与えずに変更をテストすることができます。 変更の完了後に、バージョン管理、他のチーム メンバーおよび、変更を取得でき、ビルド、テスト サーバーに配置を場所にファイルを確認します。|-   [クエリおよびテキスト エディター (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (Microsoft web サイト)<br />-   [TRANSACT-SQL デバッガー](http://go.microsoft.com/fwlink/?LinkId=227324) (Microsoft web サイト)|  
|**プロトタイプを作成、検証テストの結果、および変更データベース スクリプト オブジェクト:**使用することができます、[!INCLUDE[tsql](../data-tools/includes/tsql_md.md)]エディターいずれかの一般的なタスクの実行にします。|-   [クエリおよびテキスト エディター (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (Microsoft web サイト)|  
  
## <a name="see-also"></a>関連項目
[.NET 用の Visual Studio データ ツール](../data-tools/visual-studio-data-tools-for-dotnet.md)
