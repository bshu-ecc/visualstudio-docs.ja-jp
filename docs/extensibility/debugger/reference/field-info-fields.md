---
title: "FIELD_INFO_FIELDS |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FIELD_INFO_FIELDS
helpviewer_keywords: FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d1aa1c2363ecf3cb6bfd9531112c87d8bcaeefe4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="fieldinfofields"></a>FIELD_INFO_FIELDS
取得するには、どのような情報を指定します、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum enum_FIELD_INFO_FIELDS {   
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
typedef DWORD FIELD_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_FIELD_INFO_FIELDS {  
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
```  
  
## <a name="members"></a>メンバー  
 FIF_FULLNAME  
 初期化/を使用して、`bstrFullName`フィールドで、 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)構造体。  
  
 FIF_NAME  
 初期化/を使用して、`bstrName`フィールドで、`FIELD_INFO`構造体。  
  
 FIF_TYPE  
 初期化/を使用して、`bstrType`フィールドで、`FIELD_INFO`構造体。  
  
 FIF_MODIFIERS  
 初期化/を使用して、`bstrModifiers`フィールドで、`FIELD_INFO`構造体。  
  
## <a name="remarks"></a>コメント  
 これらの値が引数として渡されるも、 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)のどのフィールドを指定する方法、 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)構造が初期化するのには。  
  
 これらの値はでも使用、`dwFields`のメンバー、`FIELD_INFO`構造のどのフィールドが使用されていると有効なことを示します。  
  
 これらのフラグは、ビットごとと組み合わせること`OR`です。  
  
## <a name="requirements"></a>要件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)