---
title: "_aligned_msize_dbg | Microsoft Docs"
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
  - "_aligned_msize_dbg"
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
  - "_aligned_msize_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_msize_dbg"
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_msize_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙에 할당 된 메모리 블록의 크기를 반환합니다.\(디버그 버전에만 해당\)  
  
## 구문  
  
```  
size_t _aligned_msize_dbg(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### 매개 변수  
 \[in\] `memblock`  
 메모리 블록에 대한 포인터입니다.  
  
 \[in\] `alignment`  
 맞춤 값은 \-2의 정수 거듭제곱이어야 합니다.  
  
 \[in\] `offset`  
 강제로 정렬을하기 위한 메모리 할당에 대한 오프셋입니다.  
  
## 반환 값  
 부호 없는 정수 크기 \(바이트\)를 반환합니다.  
  
## 설명  
 `alignment`  및  `offset` 값은 블록을 할당 하는 함수에 전달된 값과 동일한 값이어야 합니다.  
  
 `_aligned_msize_dbg`은 [\_aligned\_msize](../../c-runtime-library/reference/aligned-msize.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의 하지 않으면,  `_aligned_msize_dbg` 의 각 호출은  `_aligned_msize` 의 호출에 감소됩니다.   `_aligned_msize`  및  `_aligned_msize_dbg`  둘 다 기본 힙에서 메모리 블록의 크기를 계산 하지만  `_aligned_msize_dbg` 는 디버깅 기능을 추가합니다: 반환 되는 크기의 메모리 블록의 사용자 부분 양쪽에 버퍼 포함.  
  
 이 함수는 매개변수를 인증합니다.   `memblock`  는 null 포인터 또는  `alignment`  2의 거듭제곱이 아닌 경우,  `_msize` 는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출합니다.  오류가 처리가된 경우, 함수는 `errno` 을 `EINVAL` 으로 설정하고, \-1을 반환합니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  할당 블록 종류 및 사용 방법에 대한 더 자세한 내용은  [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  호출 표준 힙 함수 및 응용 프로그램의 디버그 빌드에서 디버그 버전의 차이점에 대한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_msize_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)