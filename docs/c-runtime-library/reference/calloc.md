---
title: "calloc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- calloc
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
- calloc
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
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
ms.openlocfilehash: a8b0fab02487291625d67706675c62e9a737718f
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="calloc"></a>calloc
0으로 초기화된 요소가 있는 메모리에 배열을 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `num`  
 요소의 수입니다.  
  
 `size`  
 각 요소의 길이입니다(바이트).  
  
## <a name="return-value"></a>반환 값  
 `calloc`은 할당된 공간에 대한 포인터를 반환합니다. 반환 값이 가리킨 저장소 공간은 모든 형식의 개체 저장을 위해 적절하게 정렬되도록 보장됩니다. `void`가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스트를 사용합니다.  
  
## <a name="remarks"></a>설명  
 `calloc` 함수는 각각 `size`바이트 길이의 `num` 요소 배열에 대한 저장소 공간을 할당합니다. 각 요소는 0으로 초기화됩니다.  
  
 메모리 할당에 실패하거나 요청된 메모리의 양이 `_HEAP_MAXREQ`를 초과하는 경우 `calloc`은 `errno`를 `ENOMEM`으로 설정합니다. 이 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 `calloc`은 `malloc`을 호출하여, 새 처리기 모드를 설정하는 데 C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 함수를 사용합니다. 새 처리기 모드는 실패 시 `malloc`이 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다. 기본적으로 `malloc`는 메모리 할당 실패 시 새 처리기 루틴을 호출하지 않습니다. `calloc`가 메모리 할당에 실패한 경우 `malloc`이 `new` 연산자가 같은 이유로 실패했을 때 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 다음을  
  
```  
_set_new_mode(1)  
```  
  
 프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).  
  
 응용 프로그램이 디버그 버전의 C 런타임 라이브러리에 연결되면 `calloc`은 [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md)가 됩니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
 `calloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시되며, 이는 함수가 전역 변수를 수정할 수 없도록 보장되고 반환된 포인터에 별칭이 지정되지 않음을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`calloc`|\<stdlib.h> 및 \<malloc.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_calloc.c  
// This program uses calloc to allocate space for  
// 40 long integers. It initializes each element to zero.  
  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   long *buffer;  
  
   buffer = (long *)calloc( 40, sizeof( long ) );  
   if( buffer != NULL )  
      printf( "Allocated 40 long integers\n" );  
   else  
      printf( "Can't allocate memory\n" );  
   free( buffer );  
}  
```  
  
```Output  
Allocated 40 long integers  
```  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
