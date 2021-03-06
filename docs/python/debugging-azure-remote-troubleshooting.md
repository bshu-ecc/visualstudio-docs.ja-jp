---
title: "Visual Studio の Python での Azure リモート デバッグのトラブルシューティング | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 6dc28135245cae755189174b18000b5c06537b6d
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Python と Azure のリモート デバッグのトラブルシューティング

Visual Studio は、次のいずれかの理由で [リモート デバッグのための Azure App Service](debugging-azure-remote.md) へのアタッチに失敗します。

| 理由 | 解決策 |
| --- | --- |
| Visual Studio 2013 Update 4 以降がインストールされていません。 | 適切なバージョンを [visualstudio.com](https://www.visualstudio.com/downloads/) からインストールします。 | 
| App Service に配置されているプロジェクトが Visual Studio で開いているプロジェクトと一致しません。 | 正しいプロジェクトを Visual Studio に読み込みます。 |
| プロジェクトが [デバッグ] 構成で配置されていません。 | ソリューション エクスプローラーでプロジェクトを右クリックして **[発行]** を選択し、アプリケーションを再配置します。 **[設定]** タブで、**[デバッグ]** 構成が選択されていることを確認します。 |
| App Service が実行されていません。 | Visual Studio のサーバー エクスプローラーか Azure Portal から App Service を起動します。 |
| App Service が Web ソケットを使用するように構成されていません。 | [Azure Portal](https://portal.azure.com) を開いて該当の App Service に移動し、**[設定] > [アプリケーションの設定]** ブレードを開きます。**[全般設定] > [Web ソケット]** を **[オン]** にして、**[保存]** を選択します。 (このブレードに表示される **[デバッグ]** のオプションは、Python デバッグには*適用されません*。) |
| `web.debug.config` がデバッグ プロキシを無効にするように変更されています。 | このファイルを削除して、プロジェクトを App Service に再発行します。その間に Visual Studio によってファイルが再作成されます。 |

参照:

- [Python の Azure リモート デバッグ](debugging-azure-remote.md)
