---
title: "set メソッド (Float32Array) |Microsoft ドキュメント"
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
ms.assetid: 0d486ed3-72eb-4af2-b0a6-ae727c588883
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fdd3d5b350f44aaf5b96a320e0b447587c07ac22
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-float32array"></a>set メソッド (Float32Array)
値または値の配列を設定します。  
  
## <a name="syntax"></a>構文  
  
```JavaScript  
float32Array.set(index, value);  
float32Array.set(array, offset);  
  
```  
  
## <a name="parameters"></a>パラメーター  
 `index`  
 設定する位置のインデックス。  
  
 `value`  
 設定する値。  
  
 `array`  
 設定する値の型指定された配列、または型指定されていない配列。  
  
 `offset`  
 現在の配列内で値が書き込まれる位置のインデックス。  
  
## <a name="remarks"></a>コメント  
 入力配列が TypedArray の場合は、2 種類の配列で、基になる ArrayBuffer が同じであることがあります。 この場合は、すべてのデータが最初にどちらの配列とも重複しない一時バッファーにコピーされ、そこからデータが現在の配列にコピーされたかのように値が設定されます。  
  
 オフセットと指定された配列の長さを加算すると現在の TypedArray の範囲外になる場合は、例外が発生します。  
  
## <a name="example"></a>例  
 次の例は、配列の先頭の要素の設定方法を示します。  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            floatArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>要件  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]