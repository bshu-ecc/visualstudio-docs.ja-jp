---
title: "byteLength プロパティ (Int8Array) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4e8457a8-2200-4d61-800e-f49fc1e916e5
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c50f49aa7fd9665214fe4269d36766c38891f309
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="bytelength-property-int8array"></a>byteLength プロパティ (Int8Array)
読み取り専用です。 構築時に固定された、この配列の ArrayBuffer の先頭からの長さ (バイト単位)。  
  
## <a name="syntax"></a>構文  
  
```JavaScript  
var arrayByteLength = int8Array.byteLength;  
```  
  
## <a name="example"></a>例  
 配列の長さを取得する方法の例を次に示します。  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int8Array(buffer.byteLength);  
            alert(intArr.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>要件  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]