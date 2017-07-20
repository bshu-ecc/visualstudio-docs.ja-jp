---
title: "getItem メソッド (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "getItem"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "getItem メソッド"
  - "Item プロパティ"
ms.assetid: f62964ad-8b2f-4596-95d0-b20e587ecea5
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# getItem メソッド (VBArray) (JavaScript)
指定した位置にある項目を返します。  
  
## 構文  
  
```  
  
safeArray.getItem(dimension1[, dimension2, ...], dimensionN)  
```  
  
## パラメーター  
 *safeArray*  
 必須です。 VBArray オブジェクトです。  
  
 *dimension1, ..., dimensionN*  
 VBArray の目的の要素の正確な位置を指定します。*n* は、VBArray の次元数です。  
  
## 使用例  
 次の例は 3 つの部分で構成されます。 最初の部分は、Visual Basic のセーフ配列を作成する VBScript コードです。 2 番目の部分は、Visual Basic のセーフ配列に対して反復処理を行い、各要素の内容を出力する [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] コードです。 どちらの部分も HTML ページの \<HEAD\> セクションに記述します。 3 番目の部分は、他の 2 つの部分を実行するための [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] コードで、\<BODY\> セクションに記述します。  
  
```javascript  
<head>  
<script type="text/vbscript">  
<!--  
Function CreateVBArray()  
   Dim i, j, k  
   Dim a(2, 2)  
   k = 1  
   For i = 0 To 2  
      For j = 0 To 2  
         a(i, j) = k  
         document.writeln(k)  
         k = k + 1  
      Next  
      document.writeln("<BR>")  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
<script type="text/javascript">  
<!--  
function GetItemTest(vbarray)  
{  
   var i, j;  
   var a = new VBArray(vbarray);  
   for (i = 0; i <= 2; i++)  
   {  
      for (j =0; j <= 2; j++)  
      {  
         document.writeln(a.getItem(i, j));  
      }  
   }  
}  
-->  
</script>  
</head>  
<body>  
<script type="text/javascript">  
<!--  
   GetItemTest(CreateVBArray());  
-->  
</script>  
</body>  
```  
  
## 必要条件  
 Quirks、Internet Explorer 6 標準、Internet Explorer 7 標準、Internet Explorer 8 標準、Internet Explorer 9 標準、Internet Explorer 10 標準の各ドキュメント モードでサポートされます。[!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] アプリではサポートされていません。 「[バージョン情報](../../javascript/reference/javascript-version-information.md)」を参照してください。  
  
 **適用対象**: [VBArray オブジェクト](../../javascript/reference/vbarray-object-javascript.md)  
  
## 参照  
 [dimensions メソッド \(VBArray\)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [lbound メソッド \(VBArray\)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [toArray メソッド \(VBArray\)](../../javascript/reference/toarray-method-vbarray-javascript.md)   
 [ubound メソッド \(VBArray\)](../../javascript/reference/ubound-method-vbarray-javascript.md)