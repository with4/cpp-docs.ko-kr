---
title: "_CrtDumpMemoryLeaks | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDumpMemoryLeaks"
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
  - "CRTDBG_LEAK_CHECK_DF"
  - "CRTDBG_CHECK_CRT_DF"
  - "_CRTDBG_LEAK_CHECK_DF"
  - "CrtDumpMemoryLeaks"
  - "_CrtDumpMemoryLeaks"
  - "_CRTDBG_CHECK_CRT_DF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtDumpMemoryLeaks 함수"
  - "CRTDBG_LEAK_CHECK_DF 매크로"
  - "_CRTDBG_LEAK_CHECK_DF 매크로"
  - "_CrtDumpMemoryLeaks 함수"
  - "CRTDBG_CHECK_CRT_DF 매크로"
  - "_CRTDBG_CHECK_CRT_DF 매크로"
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _CrtDumpMemoryLeaks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리 누수 \(디버그 버전에만 해당\)가 발생한 경우, 디버그 힙의 모든 메모리 블록를 버립니다.  
  
## 구문  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## 반환 값  
 `_CrtDumpMemoryLeaks`는 메모리 누수를 찾으면 TRUE를 반환합니다.  그렇지 않은 경우 FALSE를 반환합니다.  
  
## 설명  
 `_CrtDumpMemoryLeaks`  함수는 시작 프로그램 실행 후 메모리 누수가 발생했는지 확인합니다.  누수가 발견되면 힙의 모든 개체에 대한 디버그 헤더 정보는 사용자가 읽을 수 있는 형태로 덤프됩니다.  [\_DEBUG](../../c-runtime-library/debug.md)가 정의되어 있지 않으면 `_CrtDumpMemoryLeaks` 에 대한 호출은 전처리 동안 제거됩니다.  
  
 `_CrtDumpMemoryLeaks`는 해제 된 응용 프로그램에서 할당된 모든 메모리를 확인하기 위해 프로그램 실행의 끝에 자주 호출됩니다.  [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수를 사용하는 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의  `_CRTDBG_LEAK_CHECK_DF`  비트 필드를 바꿈으로써 이 함수는 프로그램 종료시 자동으로 호출될 수 있습니다.  
  
 `_CrtDumpMemoryLeaks`는  [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md)을 호출하여 힙의 현재 상태를 확인하고 해제 되지 않은 상태의 블록을 검색합니다.  해제되지 않은 블록이 발견될 때,  `_CrtDumpMemoryLeaks` 는 [\_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md)을 호출하여  프로그램 실행의 시작 부분에서 힙에 할당된 모든 개체 정보를 덤프합니다.  
  
 기본적으로 내부 C 런타임 블록 \(`_CRT_BLOCK`\)은 메모리 덤프 작업에 포함되지 않습니다.   [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)함수는 누수 감지 프로세스에서 이러한 블록을 포함하기 위해   `_crtDbgFlag` 의  `_CRTDBG_CHECK_CRT_DF`  비트를 사용할 수 있습니다.  
  
 힙 상태 함수와 `_CrtMemState` 구조체에 대한 자세한 정보는 [힙 상태 보고 함수](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions) 를 참조하십시오.  기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
 `_CrtDumpMemoryLeaks` 을 사용하는 방법에 대한 예제는  [crt\_dbg1](http://msdn.microsoft.com/ko-kr/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)