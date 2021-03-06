---
title: "&lt;appAddin&gt;要素 (Visual Studio での Office 開発) |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: application manifests [Office development in Visual Studio], <appAddin> element
ms.assetid: 6152fe5b-6af1-465d-aee7-19e4fd4d04c1
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c5637a449ea40f6e4f910e061c7e2e324c91ae70
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt;要素 (Visual Studio での Office 開発)
  `appAddin` 名前空間の `vstov4` 要素には、VSTO アドイン用のカスタマイズ固有の情報が格納されます。  
  
## <a name="syntax"></a>構文  
  
```  
<appAddin  
  application  
  loadBehavior  
  keyName>  
  <friendlyName>  
  <description>  
  <formRegions></formRegions>  
</appAddin>  
```  
  
## <a name="elements-and-attributes"></a>要素と属性  
 `appAddin` 要素は必須です。この要素は `vstov4` 名前空間にあります。 アプリケーション マニフェストで定義された `appAddin` 要素が 1 つだけあります。  
  
 `appAddin` 要素には、次のような属性があります。  
  
|属性|説明|  
|---------------|-----------------|  
|`application`|必須です。 Microsoft Office アプリケーションを指定します。 この値は、Excel、InfoPath、Outlook、PowerPoint、Project、Visio、Word のいずれか 1 つになります。|  
|`loadBehavior`|省略可能です。 既定では、この値が 3 に設定され、 `loadBehavior` が有効になっています。 デバッグする場合は、この値を 2 に設定して VSTO アドインを無効にできます。 詳細については、「 [Registry Entries for VSTO Add-ins](../vsto/registry-entries-for-vsto-add-ins.md)」の表「LoadBehavior の値」を参照してください。|  
|`keyName`|必須です。 この値は、アプリケーションが VSTO アドインを読み込むのに使用するレジストリ キーの名前です。 詳細については、「 [Registry Entries for VSTO Add-ins](../vsto/registry-entries-for-vsto-add-ins.md)」を参照してください。|  
  
 `appAddin` 要素には、次の子要素があります。  
  
### <a name="friendlyname"></a>friendlyName  
 省略可能です。 `friendlyName`要素は」で説明されて[&#60; friendlyName &#62;。要素 &#40; Visual Studio &#41; での Office 開発](../vsto/friendlyname-element-office-development-in-visual-studio.md).  
  
### <a name="description"></a>説明  
 省略可能です。 `description`要素は」で説明されて[&#60;以外の場合は説明 &#62;。要素 &#40; Visual Studio &#41; での Office 開発](../vsto/description-element-office-development-in-visual-studio.md).  
  
### <a name="formregions"></a>formRegions  
 フォーム領域を含む Outlook VSTO アドインにのみ必須です。 `formRegions`要素は」で説明されて[&#60; formRegions &#62;。要素 &#40; Visual Studio &#41; での Office 開発](../vsto/formregions-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>VSTO アドインの例  
  
### <a name="description"></a>説明  
 次のコード例は、 `appAddin` を使用して配置される Outlook ソリューションの [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]要素を示しています。 このコード例は、「 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)」に記載されている例から一部を抜粋したものです。  
  
### <a name="code"></a>コード  
  
```  
<vstov4:appAddIn   
  application="Outlook"   
  loadBehavior="3"   
  keyName="ContosoOutlookAddIn">  
  <vstov4:friendlyName>  
    ContosoOutlookAddIn  
  </vstov4:friendlyName>  
  <vstov4:description>  
    ContosoOutlookAddIn - Outlook VSTO Add-in   
    created with Visual Studio Tools for Office  
  </vstov4:description>  
  <vstov4:formRegions>  
    <vstov4:formRegion  
        name="OutlookAddIn1.FormRegion1">  
      <vstov4:messageClass name="IPM.Note" />  
      <vstov4:messageClass name="IPM.Contact" />  
      <vstov4:messageClass name="IPM.Appointment" />  
    </vstov4:formRegion>  
  </vstov4:formRegions>  
</vstov4:appAddIn>  
```  
  
## <a name="see-also"></a>関連項目  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office ソリューション用配置マニフェスト](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)  
  
  