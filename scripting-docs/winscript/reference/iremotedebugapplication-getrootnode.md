---
title: "IRemoteDebugApplication::GetRootNode | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplication.GetRootNode
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplication::GetRootNode"
ms.assetid: 6c043aba-1dc5-41de-9711-96cde5e040f6
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplication::GetRootNode
アプリケーションに関連付けられているすべてのノードが追加されたアプリケーションのノードを返します。  
  
## 構文  
  
```  
HRESULT GetRootNode(  
   IDebugApplicationNode**  ppdanRoot  
);  
```  
  
#### パラメーター  
 `ppdanRoot`  
 \[入力\]アプリケーションに関連付けられているすべてのノードが追加されるデバッグ アプリケーションのノード。  
  
## 戻り値  
 このメソッドは `HRESULT` を返します。  指定できる値は、に含まれていますが、次の表に、これらはありません。  
  
|値|説明|  
|-------|--------|  
|`S_OK`|メソッドが成功しました。|  
  
## 解説  
 このメソッドは、アプリケーションに関連付けられているすべてのノードが追加されたアプリケーションのノードを返します。  
  
## 参照  
 [IRemoteDebugApplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)