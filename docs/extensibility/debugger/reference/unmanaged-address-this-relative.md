---
title: "UNMANAGED_ADDRESS_THIS_RELATIVE |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: UNMANAGED_ADDRESS_THIS_RELATIVE
helpviewer_keywords: UNMANAGED_ADDRESS_THIS_RELATIVE structure
ms.assetid: e6a91ace-2d47-4ff9-aefb-8d8b68eab0b2
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 694a41033392ccd359ddc92607652cb1fb0bb905
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="unmanagedaddressthisrelative"></a>UNMANAGED_ADDRESS_THIS_RELATIVE
この構造体が基準にあるアドレスを表す、`this`ポインター (`Me` Visual Basic で)。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef struct _tagUNMANAGED_THIS_RELATIVE {  
   DWORD dwOffset;  
   DWORD dwBitOffset;  
   DWORD dwBitLength;  
} UNMANAGED_ADDRESS_THIS_RELATIVE;  
```  
  
```csharp  
public struct UNMANAGED_THIS_RELATIVE {  
   public uint dwOffset;  
   public uint dwBitOffset;  
   public uint dwBitLength;  
}  
```  
  
## <a name="terms"></a>用語  
 dwOffset  
 基本の位置 (たとえば、クラスの vtable の先頭) からのオフセットのバイト。  
  
 dwBitOffset  
 基本の位置からのビット単位のオフセット (常に 0 のビット フィールドを参照する場合を除き)。  
  
 dwBitLength  
 アドレスを表すビット数 (常に 0 のビット フィールドを参照する場合を除き)。  
  
## <a name="remarks"></a>コメント  
 この構造体の共用体の一部である、 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)ときに構造体、`dwKind`のフィールド、`DEBUG_ADDRESS_UNION`構造に設定されている`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`(から値、 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)列挙体)。  
  
## <a name="requirements"></a>要件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)