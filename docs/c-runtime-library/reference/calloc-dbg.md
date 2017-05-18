---
title: "_calloc_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _calloc_dbg
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _calloc_dbg
- calloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 47b4e27d52235b833f01848521c85e79dbe1ffae
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="callocdbg"></a>_calloc_dbg
디버깅 헤더에 대한 추가 공간이 있는 힙에서 다수의 메모리 블록을 할당하고 버퍼를 덮어씁니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `num`  
 요청된 메모리 블록 수입니다.  
  
 `size`  
 요청된 각 메모리 블록 크기입니다(바이트).  
  
 `blockType`  
 요청된 메모리 블록 형식으로 `_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`입니다.  
  
 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
 `filename`  
 할당 작업 또는 `NULL`을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업이 요청되었거나 `NULL`인 소스 파일의 줄 번호입니다.  
  
 `filename` 및 `linenumber` 매개 변수는 `_calloc_dbg`가 명시적으로 호출되었거나 [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) 전처리기 상수가 정의된 경우에만 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료되면 이 함수는 마지막으로 할당된 메모리 블록의 사용자 부분에 대한 포인터를 반환하거나 새 처리기 함수를 호출하거나 `NULL`을 반환합니다. 반환 동작에 대한 자세한 내용은 설명 부분을 참조하세요. 새 처리기 함수를 사용하는 방법에 대한 자세한 내용은 [calloc](../../c-runtime-library/reference/calloc.md) 함수를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_calloc_dbg`는 [calloc](../../c-runtime-library/reference/calloc.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_calloc_dbg`에 대한 각 호출이 `calloc`에 대한 호출로 줄어듭니다. `calloc`과 `_calloc_dbg`가 둘 다 기본 힙의 `num` 메모리 블록을 할당하지만, `_calloc_dbg`는 다음과 같은 몇 가지 디버깅 기능을 제공합니다.  
  
-   누수를 테스트하기 위해 블록의 사용자 부분 양쪽에서 버퍼 제공.  
  
-   특정 할당 형식을 추적하기 위해 블록 형식 매개 변수 제공.  
  
-   할당 요청의 원본을 판단하기 위해 `filename`/`linenumber` 정보 제공.  
  
 `_calloc_dbg`는 요청된 `size`보다 약간 더 많은 공간이 있는 각각의 메모리 블록을 할당합니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 블록이 할당되면 블록의 사용자 부분은 값 0xCD로 채워지고 각 덮어쓰기 버퍼는 0xFD로 채워집니다.  
  
 메모리 할당에 실패하면 `_calloc_dbg`는 `errno`를 `ENOMEM`으로 설정하고 필요한 메모리 양(앞에서 언급한 오버헤드 포함)이 `EINVAL`를 초과하면 `_HEAP_MAXREQ`이 반환됩니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수를 호출하는 것과 해당 함수의 디버그 버전을 호출하는 것의 차이에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_calloc_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_callocd.c  
/*  
 * This program uses _calloc_dbg to allocate space for  
 * 40 long integers. It initializes each element to zero.  
 */  
#include <stdio.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *bufferN, *bufferC;  
  
        /*   
         * Call _calloc_dbg to include the filename and line number  
         * of our allocation request in the header and also so we can  
         * allocate CLIENT type blocks specifically  
         */  
        bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );  
        if( bufferN != NULL && bufferC != NULL )  
              printf( "Allocated memory successfully\n" );  
        else  
              printf( "Problem allocating memory\n" );  
  
        /*   
         * _free_dbg must be called to free CLIENT type blocks  
         */  
        free( bufferN );  
        _free_dbg( bufferC, _CLIENT_BLOCK );  
}  
```  
  
```Output  
Allocated memory successfully  
```  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [_DEBUG](../../c-runtime-library/debug.md)
