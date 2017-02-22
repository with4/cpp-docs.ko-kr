---
title: "_CrtMemDifference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtMemDifference"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CrtMemDifference"
  - "CrtMemDifference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtMemDifference 함수"
  - "_CrtMemDifference 함수"
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _CrtMemDifference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 메모리 상태를 비교하고 해당 차이점을 반환합니다\(디버그 버전에만 해당\).  
  
## 구문  
  
```  
int _CrtMemDifference(   
   _CrtMemState *stateDiff,  
   const _CrtMemState *oldState,  
   const _CrtMemState *newState   
);  
```  
  
#### 매개 변수  
 `stateDiff`  
 반환된 두 메모리 상태의 차이점을 저장하는 데 사용되는 `_CrtMemState` 구조에 대한 포인터입니다.  
  
 `oldState`  
 이전 메모리 상태\(`_CrtMemState` 구조\)에 대한 포인터입니다.  
  
 `newState`  
 이후 메모리 상태\(`_CrtMemState` 구조\)에 대한 포인터입니다.  
  
## 반환 값  
 메모리 상태가 현저하게 다른 경우 `_CrtMemDifference`는 TRUE를 반환합니다. 그렇지 않은 경우 이 함수는 FALSE를 반환합니다.  
  
## 설명  
 `_CrtMemDifference` 함수는 `oldState`와 `newState`를 비교하고 차이점을 `stateDiff`에 저장하여 응용 프로그램에서 메모리 누수 및 기타 메모리 문제를 감지하는 데 사용할 수 있습니다.[\_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtMemDifference`에 대한 호출이 제거됩니다.  
  
 `newState` 및 `oldState`은 각각 `_CrtMemDifference`를 호출하기 전에 [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md)에 의해 채워진, Crtdbg.h에 정의된 `_CrtMemState` 구조에 대한 유효한 포인터여야 합니다.`stateDiff`는 `_CrtMemState` 구조의 이전에 할당된 인스턴스에 대한 포인터여야 합니다.`stateDiff`, `newState` 또는 `oldState`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)는 `EINVAL`로 설정되고 함수는 FALSE를 반환합니다.  
  
 `_CrtMemDifference`는 `oldState`에 있는 블록의 `_CrtMemState` 필드 값을 `newState`의 값과 비교하고 결과를 `stateDiff`에 저장합니다. 할당된 블록 형식의 수 또는 각 형식에 대해 할당된 총 블록 수가 두 메모리 상태 간에 다를 경우 상태가 현저하게 다르다고 합니다. 두 상태에 대해 한 번에 할당된 최대 크기의 차이 및 두 상태에 대한 총 할당 수의 차이도 `stateDiff`에 저장됩니다.  
  
 기본적으로 내부 C 런타임 블록\(`_CRT_BLOCK`\)은 메모리 상태 작업에 포함되지 않습니다.[\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수는 `_CRTDBG_CHECK_CRT_DF`비트의 `_crtDbgFlag`를 설정하여 이러한 블록을 누수 감지 및 기타 메모리 상태 작업에 포함하는 데 사용할 수 있습니다. 해제된 메모리 블록\(`_FREE_BLOCK`\)으로 인해 `_CrtMemDifference`에서 TRUE를 반환하지 않습니다.  
  
 힙 상태 함수 및 `_CrtMemState` 구조에 대한 자세한 내용은 [Heap State Reporting Functions](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)를 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md)를 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_CrtMemDifference`|\<crtdbg.h\>|\<errno.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
 **라이브러리:** [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)의 디버그 버전에만 해당됩니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하세요.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)