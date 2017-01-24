---
title: "_aligned_free_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_free_dbg"
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
  - "_aligned_free_dbg"
  - "aligned_free_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_free_dbg 함수"
  - "aligned_free_dbg 함수"
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다\(디버그에만 해당\).  
  
## 구문  
  
```  
void _aligned_free_dbg(    void *memblock );  
```  
  
#### 매개 변수  
 `memblock`  
 `_aligned_malloc` 또는 `_aligned_offset_malloc` 함수로 반환된 메모리 블록에 대한 포인터입니다.  
  
## 설명  
 `_aligned_free_dbg`  함수는 [\_aligned\_free](../../c-runtime-library/reference/aligned-free.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_aligned_free_dbg`에 대한 각 호출이 \_`aligned_free`에 대한 호출로 줄어듭니다.  \_`aligned_free` 및 `_aligned_free_dbg` 함수는 둘 다 기본 힙에서 메모리 블록을 해제하지만 `_aligned_free_dbg`  함수에는 메모리 부족 조건을 시뮬레이션하기 위해 빈 블록을 힙의 연결된 목록에 보관할 수 있는 디버깅 기능이 있습니다.  
  
 `_aligned_free_dbg`는 해제 작업을 수행하기 전에 지정된 파일과 블록 위치 모두에 대해 유효성 검사를 수행합니다.  응용 프로그램에서는 이러한 유효성 검사 정보를 제공하지 않습니다.  메모리 블록이 해제되면 디버그 힙 관리자는 자동으로 사용자 부분 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다.  [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 `_CRTDBG_DELAY_FREE_MEM_DF`  비트 필드가 설정되면 빈 블록은 값 0xDD로 채워지고, 빈 블록에는 `_FREE_BLOCK` 블록 형식이 할당되고, 메모리 블록에 대한 힙의 연결된 목록에서 보관됩니다.  
  
 메모리 해제 중 오류가 발생하면 운영 체제에서 제공하는 실패 특성에 대한 정보를 바탕으로 `errno`가 설정됩니다.  자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md)를 참조하세요.  할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하세요.  응용 프로그램의 디버그 빌드 시 표준 힙 함수와 이 함수의 디버그 버전 호출 간의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_free_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)