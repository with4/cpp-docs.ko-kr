---
title: "비 MFC DLL 초기화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], 비MFC"
  - "DLL 초기화"
  - "비 MFC DLL[C++]"
ms.assetid: 2622b32a-28f9-4d61-9e46-6c19aaf8b7ad
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 비 MFC DLL 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비 MFC DLL을 초기화하려면 DLL 소스 코드에 `DllMain`이라는 함수가 포함되어 있어야 합니다.  다음 코드에서는 `DllMain` 정의의 기본 형식을 보여 줍니다.  
  
```  
BOOL APIENTRY DllMain(HANDLE hModule,   
                      DWORD  ul_reason_for_call,   
                      LPVOID lpReserved)  
{  
    switch( ul_reason_for_call ) {  
    case DLL_PROCESS_ATTACH:  
    ...  
    case DLL_THREAD_ATTACH:  
    ...  
    case DLL_THREAD_DETACH:  
    ...  
    case DLL_PROCESS_DETACH:  
    ...  
    }  
    return TRUE;  
}  
```  
  
> [!NOTE]
>  [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] 설명서에는 **DllEntryPoint**를 사용할 경우 링커 명령줄에 \/ENTRY 옵션을 사용하여 진입점 함수의 실제 이름을 지정해야 한다고 나와 있습니다.  그러나 Visual C\+\+의 경우, 진입점 함수의 이름이 `DllMain`이면 \/ENTRY 옵션을 사용하지 않아도 됩니다.  실제로, \/ENTRY 옵션을 사용하여 진입점 함수의 이름을 `DllMain`이 아닌 다른 이름으로 지정하면 C 런타임 라이브러리는 올바르게 초기화되지 않습니다.  
  
## 추가 정보  
  
-   [\<caps:sentence id\="tgt7" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>The function specification for DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic\-link library entry\-point function\(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
-   [C 런타임 라이브러리 동작 및 \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
## 참고 항목  
 [DLL 초기화](../build/initializing-a-dll.md)