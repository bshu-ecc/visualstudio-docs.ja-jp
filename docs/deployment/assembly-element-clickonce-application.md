---
title: "&lt;アセンブリ&gt;要素 (ClickOnce アプリケーション) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <assembly> element [ClickOnce application manifest]
ms.assetid: 51410569-10f9-4c0a-96b5-d39185edbefc
caps.latest.revision: "15"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: fafc5df1a2aa32fa60c1f41077f7e3fff29ddef7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="ltassemblygt-element-clickonce-application"></a>&lt;アセンブリ&gt;要素 (ClickOnce アプリケーション)
アプリケーション マニフェストの最上位要素です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      <assembly  
   manifestVersion  
/>  
```  
  
## <a name="elements-and-attributes"></a>要素と属性  
 `assembly`要素はルート要素がありが必要です。 その最初の構成要素である必要があります、`assemblyIdentity`要素。 マニフェストの要素は、次の名前空間のいずれかである必要があります。  
  
 `urn:schemas-microsoft-com:asm.v1`  
  
 `urn:schemas-microsoft-com:asm.v2`  
  
 `http://www.w3.org/2000/09/xmldsig#`  
  
 アセンブリの子要素は、これらの名前空間を継承またはタグ付けによってもする必要があります。  
  
 `assembly`要素には、次の属性です。  
  
|属性|説明|  
|---------------|-----------------|  
|`manifestVersion`|必須です。 `manifestVersion`に属性を設定する必要があります`1.0`です。|  
  
## <a name="example"></a>例  
 次のコード例を示しています、`assembly`アプリケーション マニフェストの要素、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションです。 このコード例に示されている例の一部である[ClickOnce アプリケーション マニフェスト](../deployment/clickonce-application-manifest.md)です。  
  
```  
<asmv1:assembly   
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"   
  manifestVersion="1.0"   
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">  
```  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーション マニフェスト](../deployment/clickonce-application-manifest.md)   
 [\<アセンブリ > 要素](../deployment/assembly-element-clickonce-deployment.md)