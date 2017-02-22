---
title: "_aligned_offset_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_recalloc"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "aligned_offset_recalloc"
  - "_aligned_offset_recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_offset_recalloc 함수"
  - "_aligned_offset_recalloc 함수"
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_offset_recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) 을 사용하여 할당된 메모리 블럭의 크기를 변경하고 메모리를 0으로 초기화합니다.  
  
## 구문  
  
```  
void * _aligned_offset_recalloc(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### 매개 변수  
 `memblock`  
 현재 블록 메모리 포인터입니다.  
  
 `num`  
 요소 수 입니다.  
  
 `size`  
 각 요소의 길이 \(바이트\)입니다.  
  
 `alignment`  
 맞춤 값은 \-2의 정수 거듭제곱이어야 합니다.  
  
 `offset`  
 강제로 정렬을하기 위한 메모리 할당에 대한 오프셋입니다.  
  
## 반환 값  
 `_aligned_offset_recalloc`은 재할당된\(아마 이동되었을\) 블록 메모리를 가리키는 void 포인터를 반환합니다.  만약 크기가 0이고 버퍼 인수가 `NULL`가 아니거나 혹은 주어진 크기로 블록을 확장할 충분한 메모리가 없다면 반환값은 `NULL`입니다.  첫번째 경우, 원래 블록은 해제됩니다.  두번째 경우, 원래 블록은 변경되지 않습니다.  반환 값은 모든 개체 형식의 저장소가 적절하게 정렬되도록 하는 것을 보증하는 저장 공간을 가리킵니다.  void가 아닌 형식의 포인터를 얻기 위해서, 반환 값에 형 변환을 사용합니다.  
  
 `_aligned_offset_recalloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시됩니다. 즉, 함수가 전역 변수를 수정하지 않고 반환된 포인터가 별칭이 지정되지 않도록 보증합니다.  자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md) 를 참조하십시오.  
  
## 설명  
 [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)처럼, `_aligned_offset_recalloc` 은 이 구조체내의 오프셋에서 정렬되기 위한 구조를 사용합니다.  
  
 `_aligned_offset_recalloc` 은 `malloc` 을 기반으로 합니다.  `_aligned_offset_malloc` 의 사용에 대한 자세한 내용은 [malloc](../../c-runtime-library/reference/malloc.md)을 참조하세요.  만일 `memblock` 이 `NULL` 이라면, 이 함수는 내부적으로 `_aligned_offset_malloc` 을 호출합니다.  
  
 이 함수는 메모리 할당에 실패하거나 요청된 크기\(`num` \* `size`\) 가 `_HEAP_MAXREQ` 보다 큰 경우, `errno` 를 `ENOMEM` 로 설정합니다.  `errno`에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  또한 `_aligned_offset_recalloc` 매개 변수 유효성을 검사 합니다.  만약 `alignment` 이 2의 거듭제곱이 아니거나 `offset` 이 요청된 크기와 0이 아닌 수보다 크거나 같은 경우, 이함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에서처럼 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이 함수는 `NULL` 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_offset_recalloc`|\<malloc.h\>|  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)   
 [\_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)