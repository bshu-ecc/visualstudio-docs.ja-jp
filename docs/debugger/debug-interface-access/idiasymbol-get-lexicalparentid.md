---
title: "Idiasymbol::get_lexicalparentid |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_lexicalParentId method
ms.assetid: 6c0c2874-cc47-4e4f-ad9c-02a18a108d9d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae6b36867f2c3f29c4abbbb83280c7f69eb20723
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetlexicalparentid"></a>IDiaSymbol::get_lexicalParentId
シンボルの構文上の親識別子を取得します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT get_lexicalParentId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]シンボルの構文上の親 ID を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値の`S_FALSE`プロパティは、シンボルの使用可能なことを意味します。  
  
## <a name="remarks"></a>コメント  
 識別子は、一意としてすべてのシンボルをマークする DIA SDK によって作成された一意の値です。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)