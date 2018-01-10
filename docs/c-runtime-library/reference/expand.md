---
title: "_expand | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _expand
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
dev_langs: C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 103ff4077bdc68b8886c5181ce317b5c0d0d2b79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expand"></a>_expand
메모리 블록의 크기를 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *_expand(   
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `size`  
 새 크기(바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 `_expand`는 다시 할당된 메모리 블록에 대한 void 포인터를 반환합니다. `_expand`는 `realloc`와 달리 크기를 변경할 블록을 이동할 수 없습니다. 따라서 이동하지 않고 블록을 확장할 수 있는 충분한 메모리가 있는 경우 `_expand`에 대한 `memblock` 매개 변수는 반환 값과 같습니다.  
  
 작업 중에 오류가 발견될 경우 `_expand`는 `NULL`을 반환합니다. 예를 들어 `_expand`를 사용하여 메모리 블록을 축소할 경우 작은 블록 힙의 손상이나 잘못된 블록 포인터가 발견되고 `NULL`이 반환될 수 있습니다.  
  
 이동하지 않고 블록을 지정된 크기로 확장할 수 있는 충분한 메모리가 없으면 함수는 `NULL`을 반환합니다. `_expand`는 요청된 것보다 작은 크기로 확장된 블록을 반환하지 않습니다. 오류가 발생할 경우 `errno`는 오류의 특성을 나타냅니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. 항목의 새 크기를 확인하려면 `_msize`를 사용합니다. `void`가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스트를 사용합니다.  
  
## <a name="remarks"></a>설명  
 `_expand` 함수는 힙 내에서 위치를 이동하지 않고 블록을 확장하거나 축소하여 이전에 할당된 메모리 블록의 크기를 변경합니다. `memblock` 매개 변수는 블록의 시작 부분을 가리킵니다. `size` 매개 변수는 블록의 새 크기(바이트)를 제공합니다. 블록의 콘텐츠는 새 크기와 이전 크기 중 더 짧은 크기까지 변경 사항이 없습니다. `memblock`은 해제된 메모리가 되면 안 됩니다.  
  
> [!NOTE]
>  64비트 플랫폼에서 새 크기가 현재 크기보다 작을 경우 `_expand`는 블록을 축소할 수 없습니다. 특히, 블록 크기가 16K보다 작아 블록이 낮은 조각화 힙에서 할당된 경우 `_expand`는 블록을 변경하지 않고 `memblock`을 반환합니다.  
  
 응용 프로그램이 디버그 버전의 C 런타임 라이브러리에 연결되면 `_expand`는 [_expand_dbg](../../c-runtime-library/reference/expand-dbg.md)가 됩니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `memblock`가 null 포인터인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다. `size`가 `_HEAP_MAXREQ`보다 큰 경우 `errno`는 `ENOMEM`으로 설정되고 함수는 `NULL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_expand`|\<malloc.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
```Output  
Allocate a 512 element buffer  
Allocated 512 bytes at 002C12BC  
Expanded block to 1024 bytes at 002C12BC  
```  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)