---
title: "_aligned_offset_malloc_dbg | Microsoft Docs"
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
  - "_aligned_offset_malloc_dbg"
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
  - "_aligned_offset_malloc_dbg"
  - "aligned_offset_malloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_malloc_dbg 함수"
  - "aligned_offset_malloc_dbg 함수"
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 맞춤 경계 \(디버그 버전에만 해당\)에서 메모리를 할당합니다.  
  
## 구문  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### 매개 변수  
 \[in\] `size`  
 요청된 메모리 할당의 크기입니다.  
  
 \[in\] `alignment`  
 맞춤 값은 \-2의 정수 거듭제곱이어야 합니다.  
  
 \[in\] `offset`  
 강제로 정렬을하기 위한 메모리 할당에 대한 오프셋입니다.  
  
 \[in\] `filename`  
 할당 작업 또는 NULL 요청하는 소스 파일의 이름에 대한 포인터입니다.  
  
 \[in\] `linenumber`  
 할당 작업 요청하는 소스 파일의 줄 번호 또는 NULL입니다.  
  
## 반환 값  
 할당 된 메모리 블록에 대한 포인터 또는 작업에 실패한 경우  `NULL` 입니다.  
  
## 설명  
 `_aligned_offset_malloc_dbg`은 [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의 하지 않으면,  `_aligned_offset_malloc_dbg` 의 각 호출은  `_aligned_offset_malloc` 의 호출에 감소됩니다.   `_aligned_offset_malloc`  및  `_aligned_offset_malloc_dbg`  모두  기본 힙에서 블록 메모리를 할당 하지만  `_aligned_offset_malloc_dbg` 은 몇 개의 디버깅 기능을 제공합니다: 특정 유형의 할당을 추적하는 누출 블록 타입 파라미터를 테스트하는 블록의 사용자 부분의 양쪽에 버퍼 및  할당 요청의 출처를 확인하기 위한  `filename` \/ `linenumber`  정보.  
  
 `_aligned_offset_malloc_dbg`은 요청된  `size` 보다 조금 더 많은 공간을 사용하여 메모리 블록을 할당합니다.  추가 공간은 디버그 힙 관리자가 디버그 메모리 블록을 연결하고 디버그 헤더 정보를 사용하여 응용 프로그램을 제공하고 버퍼를 덮어쓰는데 사용됩니다.  블록이 할당 될 때, 사용자의 블록 부분은 0xCD 값으로 채워지고 덮어쓰기 각 버퍼들은 0xFD로 채워집니다.  
  
 `_aligned_offset_malloc_dbg`는 중첩 된 요소에서 정렬이 필요한 경우에 유용합니다. 예를 들어, 중첩 된 클래스에 정렬이 필요한 경우.  
  
 `malloc` 을 기반으로 하는 `_aligned_offset_malloc_dbg`에 대한 자세한 내용은  [malloc](../../c-runtime-library/reference/malloc.md)을 참조하십시오.  
  
 이 함수는 메모리 할당에 실패 한 경우 또는 요청된 된 크기  `_HEAP_MAXREQ` 보다 큰 경우,   `errno`  를  `ENOMEM` 로 설정합니다.  `errno`에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  또한 `_aligned_offset_malloc` 매개 변수 유효성을 검사 합니다.   `alignment`  2의 거듭제곱이 아닌 경우,  `offset` 이  `size` 보다 크거나 같은거나 0이 아닌 경우, 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로  잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이 함수는 `NULL` 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
 할당 블록 종류 및 사용 방법에 대한 더 자세한 내용은  [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)