---
title: "コードのための自動化を提供する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa1c2fa5d0da738057e59cdac007c499a834bc0a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="providing-automation-for-code"></a>コードのための自動化を提供します。
コードのオートメーション モデルを作成する必要はありません。 環境の SDK では、これを行うためのサンプルは提供されません。 コード モデルを把握するには、次を参照してください。、<xref:EnvDTE.CodeModel>オブジェクト。  
  
 コード モデルを実装するのには、内部データ構造で定義されているインターフェイスを実装する必要があります。 派生する必要があります、オブジェクト、`IDispatch`クラスです。  
  
 オブジェクトを拡張すると、<xref:EnvDTE.CodeModel>と<xref:EnvDTE.FileCodeModel>から使用できる、<xref:EnvDTE.Project>オブジェクト、および、次のようになります。  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 実装することができますのみ`CodeModel`または`FileCodeModel`から返すオブジェクトのインターフェイス、`Project`と<xref:EnvDTE.ProjectItem>オブジェクト。 このインターフェイスは、プロジェクト システムに適したから機能が提供されます。  
  
 標準から使用できないメソッドやプロパティなどの機能を追加する場合`CodeModel`と`FileCodeModel`インターフェイスが、標準から継承するインターフェイスを作成します。 エンドユーザーが探しますがわかっているため、プロジェクト システムとドキュメントをしてください。 標準のインターフェイスを返しますが、ユーザーが呼び出すことができます、`QueryInterface`メソッドまたは存在することがわかっている場合、インターフェイスにキャストします。  
  
## <a name="see-also"></a>関連項目  
 [オートメーション モデルの概要](../../extensibility/internals/automation-model-overview.md)