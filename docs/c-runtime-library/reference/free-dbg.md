---
title: "_free_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_free_dbg"
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
  - "_free_dbg"
  - "free_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메모리 블록, 할당 해제"
  - "메모리 해제"
  - "_free_dbg 함수"
  - "free_dbg 함수"
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\(디버그 버전에만 해당\) 힙 메모리 블록을 해제합니다.  
  
## 구문  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### 매개 변수  
 `userData`  
 할당된 메모리 블록에 대한 포인터입니다.  
  
 `blockType`  
 해제하기 위해 할당된 메모리 블록의 형식:  `_CLIENT_BLOCK` ,  `_NORMAL_BLOCK` , 또는  `_IGNORE_BLOCK` .  
  
## 설명  
 `_free_dbg` 함수는 \_[해제](../../c-runtime-library/reference/free.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의 하지 않으면,  `_free_dbg` 의 각 호출은  `free` 의 호출에 감소됩니다.   `free`  와  `_free_dbg` 는 기본 힙에서 메모리 블록 해제 하지만,  `_free_dbg` 는 두 디버깅 기능을 사용할 수 있습니다: 메모리 부족 조건을 시뮬레이션 하기위해 연결된 힙의 블록을 해제하는 능력과 특정한 할당 형식을 해제하기 위한 블록 타입 매개변수.  
  
 `_free_dbg`는 사용 가능한 작업을 수행 하기 전에 지정된 모든 파일과 블록 위치에 유효성 검사를 수행합니다.  응용 프로그램은 이 정보를 사용할 수 없습니다.  메모리 블록을 해제할 경우, 디버그 힙 관리자는 자동으로 사용자 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다.  [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의  `_CRTDBG_DELAY_FREE_MEM_DF` 비트 필드가 설된 경우,해제 된 블록은  `_FREE_BLOCK` 에 할당된 0xDD 값으로 채워집니다. 그리고 메모리 블록의 힙광 연결된 리스트에 보관됩니다.  
  
 해제 된 메모리에 오류가 발생 하면  `errno` 는 오류의 성격에서 운영 체제의 정보로 설정됩니다.  자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  할당 블록 종류 및 사용 방법에 대한 더 자세한 내용은  [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  호출 표준 힙 함수 및 응용 프로그램의 디버그 빌드에서 디버그 버전의 차이점에 대한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_free_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 `_free_dbg` 을 사용하는 방법에 대한 예제는  [crt\_dbg2](http://msdn.microsoft.com/ko-kr/21e1346a-6a17-4f57-b275-c76813089167)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)