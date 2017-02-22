---
title: "_realloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_realloc_dbg"
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
  - "_realloc_dbg"
  - "realloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메모리 블록 다시 할당"
  - "realloc_dbg 함수"
  - "메모리 블록, 다시 할당"
  - "메모리, 다시 할당"
  - "_realloc_dbg 함수"
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _realloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

블록 크기를 조정하여 이동 \(디버그 버전에만 해당\)함으로써 힙 메모리의 지정된 블록의 메모리를  다시 할당합니다.  
  
## 구문  
  
```  
void *_realloc_dbg(  
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### 매개 변수  
 `userData`  
 이전에 할당 된 메모리 블록에 대 한 포인터입니다.  
  
 `newSize`  
 할당 블록 \(바이트 단위\)의 크기를 다시 요청합니다.  
  
 `blockType`  
 다시 할당된 블록에 대한 형식을 요청합니다:  `_CLIENT_BLOCK`  또는  `_NORMAL_BLOCK` .  
  
 `filename`  
 `realloc` 작업 또는 NULL을 요청하는 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 `realloc` 작업을 요청하는 소스 파일의 줄 번호 또는 NULL입니다.  
  
 `filename`  및  `linenumber`  매개 변수는  `_realloc_dbg`  가 명시적으로 호출되거나  [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) 전처리기 상수가 정의되었을 경우, 사용할 수 있습니다.  
  
## 반환 값  
 성공적으로 완료되면, 이 함수는 새로운 처리기 함수를 호출하는 재할당된 메모리 블록의 사용자 영역에 대한 포인터 또는 NULL을 반환 합니다.  반환 동작의 완벽한 설명은 아래의 설명 부분을 참조하십시오.  새 처리기 함수를 사용하는 방법에 대한 자세한 내용은 [realloc](../../c-runtime-library/reference/realloc.md)함수를 참조하십시오.  
  
## 설명  
 `_realloc_dbg`는 [realloc](../../c-runtime-library/reference/realloc.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의 하지 않으면,  `_realloc_dbg` 의 각 호출은  `realloc` 의 호출에 감소됩니다.   `realloc`  및  `_realloc_dbg` 는 모두 기본 힙에서 블록 메모리를 재할당하지만  `_realloc_dbg` 은 몇 개의 디버깅 기능을 수용합니다: 특정 유형의 할당을 추적하는 누출 블록 타입 파라미터를 테스트하는 블록의 사용자 부분의 양쪽에 버퍼 및  할당 요청의 출처를 확인하기 위한  `filename` \/ `linenumber`  정보.  
  
 `_realloc_dbg`은 요청된  `newSize` 보다 조금 더 많은 공간을 사용하여 지정된 메모리 블록을 재할당합니다.  `newSize`는 원래 할당된 메모리 블록의 크기보다 작거나 클 수 있습니다.  추가 공간은 디버그 힙 관리자가 디버그 메모리 블록을 연결하고 디버그 헤더 정보를 사용하여 응용 프로그램을 제공하고 버퍼를 덮어쓰는데 사용됩니다.  재할당은 메모리 블록의 크기를 변경 뿐만 아니라 힙의 다른 위치에 원래 메모리 블록을 이동할 수 있습니다.  메모리 블록을 이동하는 경우, 원래 블록의 내용은 덮어씁니다.  
  
 앞에서 설명한 오버 헤드 등 필요한 메모리 양이  `_HEAP_MAXREQ` 를 초과하거나 메모리 할당이 실패할 경우, `_realloc_dbg`은  `errno`  를  `ENOMEM` 로 설정합니다.  이 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  할당 블록 종류 및 사용 방법에 대한 더 자세한 내용은  [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  호출 표준 힙 함수 및 응용 프로그램의 디버그 빌드에서 디버그 버전의 차이점에 대한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_realloc_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
 [\_msize\_dbg](../../c-runtime-library/reference/msize-dbg.md)항목에서 예제를 참고하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)