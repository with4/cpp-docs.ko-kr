---
title: "_aligned_malloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_malloc"
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
  - "_aligned_malloc"
  - "alligned_malloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_malloc 함수"
  - "aligned_malloc 함수"
ms.assetid: fb788d40-ee94-4039-aa4d-97d73dab1ca0
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _aligned_malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 맞춤 경계에 메모리를 할당합니다.  
  
## 구문  
  
```  
void * _aligned_malloc(  
    size_t size,   
    size_t alignment  
);  
```  
  
#### 매개 변수  
 `size`  
 요청된 메모리 할당의 크기입니다.  
  
 `alignment`  
 2의 정수 제곱이어야 하는 맞춤 값입니다.  
  
## 반환 값  
 할당된 메모리 블록에 대한 포인터로 작업 실패 시 `NULL`입니다.  포인터는 `alignment`의 배수입니다.  
  
## 설명  
 `_aligned_malloc`는 [malloc](../../c-runtime-library/reference/malloc.md)를 기반으로 합니다.  
  
 `_aligned_malloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시되며, 이는 함수가 전역 변수를 수정할 수 없도록 보장되고 반환된 포인터에 별칭이 지정되지 않음을 의미합니다.  자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.  
  
 이 함수는 메모리 할당에 실패한 경우 또는 요청된 크기가 `errno`보다 큰 경우 `ENOMEM`를 `_HEAP_MAXREQ`으로 설정합니다.  `errno`에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  또한 `_aligned_malloc`는 매개 변수의 유효성을 검사합니다.  `alignment`가 2의 거듭제곱이 아니거나 `size`가 0인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용한 경우 이 함수는 `NULL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_malloc`|\<malloc.h\>|  
  
## 예제  
  
```  
// crt_aligned_malloc.c  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main() {  
    void    *ptr;  
    size_t  alignment,  
            off_set;  
  
    // Note alignment should be 2^N where N is any positive int.  
    alignment = 16;  
    off_set = 5;  
  
    // Using _aligned_malloc  
    ptr = _aligned_malloc(100, alignment);  
    if (ptr == NULL)  
    {  
        printf_s( "Error allocation aligned memory.");  
        return -1;  
    }  
    if (((unsigned long long)ptr % alignment ) == 0)  
        printf_s( "This pointer, %p, is aligned on %zu\n",  
                  ptr, alignment);  
    else  
        printf_s( "This pointer, %p, is not aligned on %zu\n",   
                  ptr, alignment);  
  
    // Using _aligned_realloc  
    ptr = _aligned_realloc(ptr, 200, alignment);  
    if ( ((unsigned long long)ptr % alignment ) == 0)  
        printf_s( "This pointer, %p, is aligned on %zu\n",  
                  ptr, alignment);  
    else  
        printf_s( "This pointer, %p, is not aligned on %zu\n",   
                  ptr, alignment);  
    _aligned_free(ptr);  
  
    // Using _aligned_offset_malloc  
    ptr = _aligned_offset_malloc(200, alignment, off_set);  
    if (ptr == NULL)  
    {  
        printf_s( "Error allocation aligned offset memory.");  
        return -1;  
    }  
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)  
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",  
                  ptr, off_set, alignment);  
    else  
        printf_s( "This pointer, %p, does not satisfy offset %zu "  
                  "and alignment %zu\n",ptr, off_set, alignment);  
  
    // Using _aligned_offset_realloc  
    ptr = _aligned_offset_realloc(ptr, 200, alignment, off_set);  
    if (ptr == NULL)  
    {  
        printf_s( "Error reallocation aligned offset memory.");  
        return -1;  
    }  
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)  
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",  
                  ptr, off_set, alignment);  
    else  
        printf_s( "This pointer, %p, does not satisfy offset %zu and "  
                  "alignment %zu\n", ptr, off_set, alignment);  
  
    // Note that _aligned_free works for both _aligned_malloc  
    // and _aligned_offset_malloc. Using free is illegal.  
    _aligned_free(ptr);  
}  
```  
  
  **이 포인터 3280880은 16에 맞춰집니다.**  
**이 포인터 3280880은 16에 맞춰집니다.**  
**이 포인터 3280891은 16 맞춤에서 5만큼 오프셋됩니다.**  
**이 포인터 3280891은 16 맞춤에서 5만큼 오프셋됩니다.**   
## 참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)