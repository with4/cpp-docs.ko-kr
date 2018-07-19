---
title: _heapset | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
dev_langs:
- C++
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c45c4cc3e6e6ffe23378ce0b4f26383369e92058
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391589"
---
# <a name="heapset"></a>_heapset
힙에서 최소한의 일관성을 검사하고 사용 가능한 항목을 지정된 값으로 설정합니다.  
  
> [!IMPORTANT]
>  이 함수는 사용되지 않습니다. Visual Studio 2015부터 CRT에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _heapset(   
   unsigned int fill   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fill`  
 채우기 문자.  
  
## <a name="return-value"></a>반환 값  
 `_heapset`는 Malloc.h에 정의된 다음 정수 매니페스트 상수 중 하나를 반환합니다.  
  
 `_HEAPBADBEGIN`  
 초기 헤더 정보가 잘못되었거나 없습니다.  
  
 `_HEAPBADNODE`  
 힙이 손상되었거나 잘못된 노드가 있습니다.  
  
 `_HEAPEMPTY`  
 힙이 초기화되지 않았습니다.  
  
 `_HEAPOK`  
 힙이 일치하는 것 같습니다.  
  
 또한 오류가 발생하는 경우 `_heapset` 는 `errno` 를 `ENOSYS`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `_heapset` 함수는 실수로 덮어쓴 사용 가능한 메모리 위치 또는 노드를 표시합니다.  
  
 `_heapset` 는 힙에서 최소한의 일관성을 검사한 다음 힙에서 사용 가능한 항목의 각 바이트를 `fill` 값으로 설정합니다. 이 알려진 값은 사용 가능한 노드를 포함하는 힙의 메모리 위치와 해제된 메모리에 실수로 기록된 데이터를 포함하는 메모리 위치를 표시합니다. 운영 체제가 `_heapset`(예: Windows 98)을 지원하지 않는 경우 함수에서 `_HEAPOK`를 반환하고 `errno`를 `ENOSYS`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_heapset`|\<malloc.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_heapset.c  
// This program checks the heap and  
// fills in free entries with the character 'Z'.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int heapstatus;  
   char *buffer;  
  
   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is   
      exit( 0 );                        //    initialized       
   heapstatus = _heapset( 'Z' );        // Fill in free entries   
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf( "OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf( "OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
   free( buffer );  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../c-runtime-library/memory-allocation.md)   
 [_heapadd](../c-runtime-library/heapadd.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)