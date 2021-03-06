---
title: "IDiaStackWalker |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalker interface
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e651c8ba8bee152121b96b14613144768a56cc2f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalker"></a>IDiaStackWalker
.Pdb ファイルに情報を使用して、スタックを行う方法の説明を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
IDiaStackWalker: IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDiaStackWalker`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|X86 用のスタック フレームの列挙子を取得プラットフォームです。|  
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|特定のプラットフォームの種類のスタック フレームの列挙子を取得します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスを使用して、読み込まれたモジュールのスタック フレームの一覧を取得します。 各メソッドに渡される、 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) (クライアント アプリケーションによって実装される) のスタック フレームのリストを作成するために必要な情報を提供するオブジェクト。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 このインターフェイスは呼び出すことによって取得、`CoCreateInstance`クラス識別子を持つメソッド`CLSID_DiaStackWalker`とのインターフェイス ID`IID_IDiaStackWalker`です。 この例では、このインターフェイスを取得する方法を示します。  
  
## <a name="example"></a>例  
 この例は、取得する方法を示します、`IDiaStackWalker`インターフェイスです。  
  
```C++  
  
      IDiaStackWalker* pStackWalker;  
HRESULT hr = CoCreateInstance(CLSID_DiaStackWalker,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaStackWalker,  
                              (void**) &pStackWalker);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>要件  
 ヘッダー: Dia2.h  
  
 ライブラリ: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>関連項目  
 [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)