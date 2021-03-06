---
title: Azure SDK for Python | Microsoft Docs
ms.custom: 
ms.date: 3/7/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: ca0318e84c3bb8787b1a499f83d11389699817f2
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="azure-sdk-for-python"></a>Azure SDK for Python

Azure SDK for Python を使用すると、Windows、Mac OSX、Linux で実行されているアプリケーションからの Microsoft Azure サービスの使用と管理が簡単になります。

## <a name="installation"></a>インストール

Azure SDK は [Python のパッケージ インデックス](https://pypi.python.org/pypi/azure)からインストールします。

次のように、**最新の安定したバージョン** (Python 2.7 および 3.3+ をサポート) をインストールします。

```bash
pip install azure
```

Azure ドキュメントの「[Python と SDK のインストール](https://azure.microsoft.com/documentation/articles/python-how-to-install/)」の手順に従ってインストールすることもできます。

## <a name="documentation"></a>ドキュメント

ドキュメントは [azure-sdk-for-python.readthedocs.org](http://azure-sdk-for-python.readthedocs.org/en/latest/index.html) にあります。

「[Python デベロッパー センター](http://azure.microsoft.com/develop/python/)」にも、次のようなさまざまなチュートリアルを含む有用なリソースが数多く用意されています。

  - [Django](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-django-app)、[Flask](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-flask-app)、[Bottle](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-bottle-app) を使用した Web アプリの作成
  - [Python から Azure BLOB ストレージを使用する方法](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-blob-storage)
  - [Python から Table ストレージを使用する方法](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-table-storage)
  - [Python から Queue ストレージを使用する方法](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-queue-storage)
  - [DocumentDB を使用した Python Flask Web アプリケーションの作成](https://docs.microsoft.com/azure/documentdb/documentdb-python-application)
  - [Service Bus キューの使用方法](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
  - [Service Bus のトピックとサブスクリプションの使用方法](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
  - [Python からサービス管理を使用する方法](https://docs.microsoft.com/azure/cloud-services/cloud-services-python-how-to-use-service-management)

ドキュメントのないパブリック API に関しては、[SDK の GitHub リポジトリ](https://github.com/Azure/azure-sdk-for-python)が有益な情報源になります。

- [ストレージの単体テスト](https://github.com/Azure/azure-storage-python/tree/master/tests)に関するページ
- [Service Bus の単体テスト](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)に関するページ
- [サービス管理の単体テスト](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)に関するページ
- [リソース管理の単体テスト](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)に関するページ

## <a name="support"></a>サポート

SDK の Git リポジトリは [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python) にあります。

SDK の使用方法についての問題や質問がある場合は、[リポジトリに問題を登録してください](https://github.com/Azure/azure-sdk-for-python/issues)。
