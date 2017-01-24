---
title: "_aligned_malloc_dbg | Microsoft Docs"
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
  - "_aligned_malloc_dbg"
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
  - "_aligned_malloc_dbg"
  - "aligned_malloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_malloc_dbg 함수"
  - "aligned_malloc_dbg 함수"
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디버깅 헤더에 대한 추가 공간이 있는 지정된 정렬 경계에서 메모리 블록을 할당하고 버퍼를 덮어씁니다\(디버그 버전에만 해당\).  
  
## 구문  
  
```  
void * _aligned_malloc_dbg(     size_t size,      size_t alignment,    const char *filename,    int linenumber  );  
```  
  
#### 매개 변수  
 \[in\] `size`  
 요청된 메모리 할당 크기입니다.  
  
 \[in\] `alignment`  
 맞춤 값으로 2의 정수 거듭제곱이어야 합니다.  
  
 \[in\] `filename`  
 할당 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 \[in\] `linenumber`  
 할당 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.  
  
## 반환 값  
 할당된 메모리 블록에 대한 포인터로 작업 실패 시 `NULL`입니다.  
  
## 설명  
 `_aligned_malloc_dbg`는 [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_aligned_malloc_dbg`에 대한 각 호출이 `_aligned_malloc`에 대한 호출로 줄어듭니다.  `_aligned_malloc`와 `_aligned_malloc_dbg` 둘 다 기본 힙에서 메모리 블록을 할당하지만 `_aligned_malloc_dbg`는 여러 디버깅 특징, 즉 누수를 테스트하기 위한 블록의 사용자 부분 양쪽에서의 버퍼 및 할당 요청의 원점을 확인하기 위한 `filename`\/`linenumber` 정보를 제공합니다.  
  
 `_aligned_malloc_dbg`는 요청된 `size`보다 약간 큰 공간의 메모리 블록을 할당합니다.  디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다.  블록이 할당되면 블록의 사용자 부분은 값 0xCD로 채워지고 각 덮어쓰기 버퍼는 0xFD로 채워집니다.  
  
 메모리 할당에 실패한 경우 또는 필요한 메모리 양\(앞에서 언급한 오버헤드 포함\)이 `_HEAP_MAXREQ`를 초과한 경우 `_aligned_malloc_dbg`는 `errno`를 `ENOMEM`으로 설정합니다.  이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  또한 `_aligned_malloc_dbg`는 매개 변수의 유효성을 검사합니다.  `alignment`가 2의 거듭제곱이 아니거나 `size`가 0인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명하는 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용한 경우 이 함수는 `NULL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md)를 참조하세요.  할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하세요.  응용 프로그램의 디버그 빌드 시 표준 힙 함수와 이 함수의 디버그 버전 호출 간의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_malloc_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 디버그 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)