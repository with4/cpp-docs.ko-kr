---
title: "_recalloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_recalloc_dbg"
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
  - "recalloc_dbg"
  - "_recalloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_recalloc_dbg 함수"
  - "recalloc_dbg 함수"
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _recalloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

배열을 다시 할당하고 배열의 요소를 0으로 초기화합니다\(디버그 버전에만 해당\).  
  
## 구문  
  
```  
void *_recalloc_dbg(     void *userData,    size_t num,    size_t size,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### 매개 변수  
 `userData`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `num`  
 요청된 메모리 블록 수입니다.  
  
 `size`  
 요청된 각 메모리 블록 크기입니다\(바이트\).  
  
 `blockType`  
 요청된 메모리 블록 형식으로 `_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`입니다.  
  
 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하세요.  
  
 `filename`  
 할당 작업 또는 `NULL`을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업이 요청되었거나 `NULL`인 소스 파일의 줄 번호입니다.  
  
 `filename` 및 `linenumber` 매개 변수는 `_recalloc_dbg`가 명시적으로 호출되었거나 [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) 전처리기 상수가 정의된 경우에만 사용할 수 있습니다.  
  
## 반환 값  
 성공적으로 완료되면 이 함수는 다시 할당된 메모리 블록의 사용자 부분에 대한 포인터를 반환하거나 새 처리기 함수를 호출하거나 NULL을 반환합니다.  반환 동작에 대한 자세한 설명은 다음 설명 섹션을 참조하세요.  새 처리기 함수 사용 방법에 대한 자세한 내용은 [\_recalloc](../../c-runtime-library/reference/recalloc.md) 함수를 참조하세요.  
  
## 설명  
 `_recalloc_dbg`는 [\_recalloc](../../c-runtime-library/reference/recalloc.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_recalloc_dbg`에 대한 각 호출이 `_recalloc`에 대한 호출로 줄어듭니다.  `_recalloc`와 `_recalloc_dbg` 둘 다 기본 힙에서 메모리 블록을 다시 할당하지만 `_recalloc_dbg`는 여러 디버깅 기능을 수용합니다. 이러한 기능에는 메모리 블록의 사용자 부분 한 쪽에서의 버퍼\(어느 쪽이든지 상관없이\)로 누수 테스트, 블록 형식 매개 변수로 특정 할당 형식 추적 및 `filename`\/`linenumber` 정보로 할당 요청의 원점을 확인하는 기능이 있습니다.  
  
 `_recalloc_dbg`는 요청된 크기\(`num` \* `size`\)보다 약간 더 많은 공간을 지정된 메모리 블록에 다시 할당합니다. 이때, 요청된 크기는 원래 할당된 메모리 블록의 크기보다 더 크거나 작을 수 있습니다.  디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다.  다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다.  블록의 사용자 부분은 값 0xCD로 채워지고 각 덮어쓰기 버퍼는 0xFD로 채워집니다.  
  
 메모리 할당에 실패하면 `_recalloc_dbg`는 `errno`를 `ENOMEM`으로 설정하고 필요한 메모리 양\(앞에서 언급한 오버헤드 포함\)이 `_HEAP_MAXREQ`를 초과하면 `EINVAL`이 반환됩니다.  이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md)를 참조하세요.  응용 프로그램의 디버그 빌드 시 표준 힙 함수와 이 함수의 디버그 버전 호출 간의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_recalloc_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 디버그 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)