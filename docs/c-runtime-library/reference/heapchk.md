---
title: "_heapchk | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _heapchk
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
- _heapchk
- heapchk
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d75464be51440dfd171323ad91d32946310ea956
ms.lasthandoff: 02/24/2017

---
# <a name="heapchk"></a>_heapchk
힙에서 일관성 확인을 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _heapchk( void );  
```  
  
## <a name="return-value"></a>반환 값  
 `_heapchk`는 Malloc.h에 정의된 다음 정수 매니페스트 상수 중 하나를 반환합니다.  
  
 `_HEAPBADBEGIN`  
 초기 헤더 정보가 잘못되었거나 찾을 수 없습니다.  
  
 `_HEAPBADNODE`  
 잘못된 노드가 검색되었거나 힙이 손상되었습니다.  
  
 `_HEAPBADPTR`  
 힙 포인터가 잘못되었습니다.  
  
 `_HEAPEMPTY`  
 힙이 초기화되지 않았습니다.  
  
 `_HEAPOK`  
 힙이 일치하는 것 같습니다.  
  
 또한 오류가 발생하는 경우 `_heapchk` 는 `errno` 를 `ENOSYS`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `_heapchk` 함수를 통해 힙의 최소 일관성을 확인하여 힙 관련 문제를 디버그할 수 있습니다. 운영 체제가 `_heapchk`(예: Windows 98)를 지원하지 않는 경우 함수에서 `_HEAPOK`를 반환하고 `errno`를 `ENOSYS`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_heapchk`|\<malloc.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)   
 [_heapwalk](../../c-runtime-library/reference/heapwalk.md)
