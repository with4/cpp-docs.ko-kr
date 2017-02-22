---
title: "_CrtMemDumpAllObjectsSince | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtMemDumpAllObjectsSince"
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
  - "CrtMemDumpAllObjectsSince"
  - "_CrtMemDumpAllObjectsSince"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtMemDumpAllObjectsSince 함수"
  - "CrtMemDumpAllObjectsSince 함수"
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _CrtMemDumpAllObjectsSince
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙에서 지정한 힙 상태 \(디버그 버전에만 해당\) 또는 프로그램 실행의 시작 부분에서 개체 정보를 덤프합니다.  
  
## 구문  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### 매개 변수  
 `state`  
 시작에서 덤프 힙 상태에 대한 포인터 또는  **NULL**.  
  
## 설명  
 `_CrtMemDumpAllObjectsSince`  함수는 사용자가 읽을 수 있는 형태로 힙에 할당 된 개체의 디버그 헤더 정보를 덤프합니다.  덤프 정보는 응용 프로그램이 메모리를 할당하고 탐지하는 과정에서 발생한 문제를 추적하는 데에 사용할 수 있습니다.  [\_DEBUG](../../c-runtime-library/debug.md)가 정의되어 있지 않으면 `_CrtMemDumpAllObjectsSince` 에 대한 호출은 전처리 동안 제거됩니다.  
  
 `_CrtMemDumpAllObjectsSince`는  `state`  매개변수의 값을 사용하여 덤프 작업을 시작 하는 위치를 확인할 수 있습니다.  지정된 힙 상태에서 덤프를 시작하려면  `state`  매개 변수는 **\_CrtMemState** 구조의 포인터여야 합니다. 해당 포인터는  `_CrtMemDumpAllObjectsSince`  호출되기 전에 [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md)로 채워져있습니다.   `state` 가 **NULL**일 때, 함수는 프로그램 실행의 시작 부분에서 덤프를 시작합니다.  
  
 응용 프로그램이 [\_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md)를 호출하여 덤프 후크 함수를 설치하는 경우,  `_CrtMemDumpAllObjectsSince` 가 블록의  `_CLIENT_BLOCK` 형식에 대한 정보를 덤프할 때마다, 응용 프로그램에서 제공한 덤프 함수를 호출합니다.  기본적으로 내부 C 런타임 블록 \(`_CRT_BLOCK`\)은 메모리 덤프 작업에 포함되지 않습니다.   [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수는 **\_crtDbgFlag**의  `_CRTDBG_CHECK_CRT_DF`  비트를 이러한 블록을 포함하도록 바꿀 때 사용됩니다.  또한, 해제 또는 무시같이 표시된 블록은 \(**\_FREE\_BLOCK**,  **\_IGNORE\_BLOCK**\) 메모리 덤프에 포함되지 않습니다.  
  
 힙 상태 함수와 `_CrtMemState` 구조체에 대한 자세한 정보는 [힙 상태 보고 함수](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions) 를 참조하십시오.  기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**\_CrtMemDumpAll\-ObjectsSince**|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
 `_CrtMemDumpAllObjectsSince` 을 사용하는 방법에 대한 예제는  [crt\_dbg2](http://msdn.microsoft.com/ko-kr/21e1346a-6a17-4f57-b275-c76813089167)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)