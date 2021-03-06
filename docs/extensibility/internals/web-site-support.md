---
title: "Web サイト サポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7a34a964450931071a290764074f4e955fe19aea
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="web-site-support"></a>Web サイトのサポート
Web サイト プロジェクト システムは、Web プロジェクトを作成するプロジェクト システムです。 Web プロジェクトは、Web アプリケーションを作成します。 Web サイト プロジェクトでは、コードが関連付けられている Web ページごとに 1 つの実行可能ファイルを生成します。 場合は/App_Code フォルダー内のソース コード ファイルから追加の実行可能ファイルが生成されます。  
  
 Web サイト プロジェクト システムは、既存のプロジェクト システムにテンプレートおよび登録属性を追加することによって作成されます。 これらの属性のいずれかには、言語の IntelliSense プロバイダーが選択されます。 IntelliSense のプロバイダーの実装では、参照を処理し、スマート Web ページがキャッシュされていないことを要求するときに、言語コンパイラを呼び出します。  
  
 Web ページをコンパイルするために使用する言語コンパイラに登録する必要があります[!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]です。 使用することができます、 [\<コンパイラ > 要素](/dotnet/framework/configure-apps/file-schema/compiler/compiler-element)次の例のように、コンパイラを登録する Web.config ファイルで。  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Web サイト サポートのテンプレート](../../extensibility/internals/web-site-support-templates.md)  
 新しい Web サイト プロジェクトと関連付けられた項目の作成に使用できるテンプレートの一覧を表示します。  
  
 [Web サイト サポートの属性](../../extensibility/internals/web-site-support-attributes.md)  
 表示する Web サイト プロジェクトを接続している登録属性[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]と[!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]です。  
  
## <a name="related-sections"></a>関連項目  
 [Web プロジェクト](../../extensibility/internals/web-projects.md)  
 Web プロジェクト、Web サイト プロジェクトおよび Web アプリケーション プロジェクトの 2 種類の概要を示します。