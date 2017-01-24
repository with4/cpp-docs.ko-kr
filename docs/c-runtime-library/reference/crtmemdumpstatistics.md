---
title: "_CrtMemDumpStatistics | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtMemDumpStatistics"
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
  - "CrtMemDumpStatistics"
  - "_CrtMemDumpStatistics"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtMemDumpStatistics 함수"
  - "CrtMemDumpStatistics 함수"
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtMemDumpStatistics
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 힙 상태에 대한 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다\(디버그 버전에만 해당\).  
  
## 구문  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### 매개 변수  
 `state`  
 덤프할 힙 상태에 대한 포인터입니다.  
  
## 설명  
 `_CrtMemDumpStatistics` 함수는 지정된 힙 상태에 대한 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다. 덤프 통계는 응용 프로그램에서 할당을 추적하고 메모리 문제를 감지하는 데 사용할 수 있습니다. 메모리 상태에는 특정 힙 상태나 두 상태 간의 차이가 포함될 수 있습니다.[\_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtMemDumpStatistics`에 대한 호출이 제거됩니다.  
  
 `state` 매개 변수는 `_CrtMemDumpStatistics`가 호출되기 전에 [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md)에 의해 채워지거나 [\_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)에서 반환된 `_CrtMemState` 구조에 대한 포인터여야 합니다.`state`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `errno`는 `EINVAL`로 설정되고 아무 동작도 수행되지 않습니다. 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 힙 상태 함수 및 `_CrtMemState` 구조에 대한 자세한 내용은 [Heap State Reporting Functions](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)를 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md)를 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h\>|\<errno.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
 **라이브러리:** [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)의 디버그 버전에만 해당됩니다.  
  
## 해당 .NET Framework 항목  
 <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName>  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)