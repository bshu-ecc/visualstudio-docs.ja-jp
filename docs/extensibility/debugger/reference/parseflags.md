---
title: "PARSEFLAGS |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PARSEFLAGS
helpviewer_keywords: PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c96eb60c397093fb5ec3291a0b02ee7cbd07e34
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="parseflags"></a>PARSEFLAGS
式を解析する方法を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
typedef DWORD PARSEFLAGS;  
```  
  
```csharp  
public enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
```  
  
## <a name="members"></a>メンバー  
 PARSE_EXPRESSION  
 式がステートメントでないことを示します。  
  
 PARSE_FUNCTION_AS_ADDRESS  
 式が解析 (および後で評価) アドレスとしてのことを示します。  
  
 PARSE_DESIGN_TIME_EXPR_EVAL  
 デザイン時に式が解析されていることを示します (つまり、デザイナーが開いているとき)。  
  
## <a name="remarks"></a>コメント  
 パラメーターとして渡される、 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)と[解析](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)メソッドです。  
  
## <a name="requirements"></a>要件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [解析](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)