---
title: PROFILE_CURRENTID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: PROFILE_CURRENTID
ms.assetid: 55ccf665-a05e-48c3-adf7-7714c0a9aaef
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eaf85776b08f6df56b5e441d9e0c99e239bf8ca6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="profilecurrentid"></a>PROFILE_CURRENTID
PROFILE_CURRENTID は、NameProfile、StartProfile、StopProfile、SuspendProfile、および ResumeProfile の各関数呼び出しで、スレッド ID またはプロセス ID の疑似トークンを返します。 指定されたスレッドやプロセスではなく、現在のスレッドまたはプロセスで関数を実行する場合に使用します。  
  
## <a name="example"></a>例  
 PROFILE_CURRENTID は VSPerf.h で次のように定義されます。  
  
```  
static const unsigned int PROFILE_CURRENTID = (unsigned int)-1;  
```  
  
## <a name="example"></a>例  
 PROFILE_CURRENTID の例を以下に示します。 この例では、[StartProfile](../profiling/startprofile.md) 関数の呼び出しで現在のスレッドを識別するパラメーターとして、PROFILE_CURRENTID を使用しています。  
  
```  
void ExerciseProfileCurrentID()  
{  
    // Declare ProfileOperationResult enumeration   
    // to hold return value of a call to StartProfile.  
    PROFILE_COMMAND_STATUS profileResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    profileResult = StartProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("StartProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio プロファイラー API リファレンス (ネイティブ)](../profiling/visual-studio-profiler-api-reference-native.md)   
 [NameProfile](../profiling/nameprofile.md)   
 [ResumeProfile](../profiling/resumeprofile.md)   
 [StartProfile](../profiling/startprofile.md)   
 [StopProfile](../profiling/stopprofile.md)   
 [SuspendProfile](../profiling/suspendprofile.md)