---
title: "_aligned_offset_malloc | Microsoft Docs"
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
  - "_aligned_offset_malloc"
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
  - "_aligned_offset_malloc"
  - "aligned_offset_malloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_aligned_offset_malloc 함수"
  - "aligned_offset_malloc 함수"
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 맞춤 경계에 메모리를 할당합니다.  
  
## 구문  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### 매개 변수  
 \[in\] `size`  
 요청된 메모리 할당의 크기입니다.  
  
 \[in\] `alignment`  
 맞춤 값은 \-2의 정수 거듭제곱이어야 합니다.  
  
 \[in\] `offset`  
 강제로 정렬을하기 위한 메모리 할당에 대한 오프셋입니다.  
  
## 반환 값  
 할당 된 메모리 블록에 대한 포인터 또는 작업에 실패한 경우  `NULL` 입니다.  
  
## 설명  
 `_aligned_offset_malloc`는 중첩 된 요소에서 정렬이 필요한 경우에 유용합니다. 예를 들어, 중첩 된 클래스에 정렬이 필요한 경우.  
  
 `malloc` 을 기반으로 하는 `_aligned_offset_malloc`에 대한 자세한 내용은  [malloc](../../c-runtime-library/reference/malloc.md)을 참조하십시오.  
  
 `_aligned_offset_malloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시됩니다. 즉, 함수가 전역 변수를 수정하지 않고 반환된 포인터가 별칭이 지정되지 않도록 보증합니다.  자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md) 를 참조하십시오.  
  
 이 함수는 메모리 할당에 실패 한 경우 또는 요청된 된 크기  `_HEAP_MAXREQ` 보다 큰 경우,   `errno`  를  `ENOMEM` 로 설정합니다.  `errno`에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  또한 `_aligned_offset_malloc` 매개 변수 유효성을 검사 합니다.   `alignment`  2의 거듭제곱이 아닌 경우,  `offset` 이  `size` 보다 크거나 같은거나 0이 아닌 경우, 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로  잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이 함수는 `NULL` 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_offset_malloc`|\<malloc.h\>|  
  
## 예제  
 더 자세한 내용은 [\_malloc\_dbg](../../c-runtime-library/reference/aligned-malloc.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)