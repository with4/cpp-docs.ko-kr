---
title: qsort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort
dev_langs:
- C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a39f6edf9dfdf2130bfe9d00cc2a9453f48ad9f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="qsort"></a>qsort
빠른 정렬을 수행합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [qsort_s](../../c-runtime-library/reference/qsort-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `base`  
 대상 배열의 시작 부분입니다.  
  
 `num`  
 요소의 배열 크기입니다.  
  
 `width`  
 요소 크기(바이트)입니다.  
  
 `compare`  
 두 배열 요소를 비교하여 해당 관계를 지정하는 값을 반환하는 사용자가 제공한 루틴에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `qsort`함수는 빠른 정렬 알고리즘을 구현하여 `num` 요소(각각 `width`바이트)의 배열을 정렬합니다. `base` 인수는 정렬할 배열의 밑에 대한 포인터입니다. `qsort`는 정렬된 요소를 사용하여 이 배열을 덮어씁니다.  
  
 `qsort`는 정렬 중에 `compare` 루틴을 한 번 이상 호출하며 각 호출에서 두 배열 요소에 포인터를 전달합니다.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 루틴은 요소를 비교한 후에 다음 값 중 하나를 반환합니다.  
  
|비교 함수 반환 값|설명|  
|-----------------------------------|-----------------|  
|< 0|`elem1`이 `elem2`보다 짧음|  
|0|`elem1`이 `elem2`와 같음|  
|> 0|`elem1` > `elem2`|  
  
 비교 함수에 정의된 대로 배열은 오름차순으로 정렬됩니다. 배열을 내림차순으로 정렬하려면 비교 함수에서 "보다 큼"과 "보다 작음"의 의미를 반전하면 됩니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `compare` 또는 `num`이 `NULL`이거나, `base`가 `NULL`이고 *`num`이 0이 아니거나, `width`가 0보다 작으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수가 반환되고 `errno`가 `EINVAL`로 설정됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`qsort`|\<stdlib.h> 및 \<search.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_qsort.c  
// arguments: every good boy deserves favor  
  
/* This program reads the command-line  
 * parameters and uses qsort to sort them. It  
 * then displays the sorted arguments.  
 */  
  
#include <stdlib.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main( int argc, char **argv )  
{  
   int i;  
   /* Eliminate argv[0] from sort: */  
   argv++;  
   argc--;  
  
   /* Sort remaining args using Quicksort algorithm: */  
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );  
  
   /* Output sorted list: */  
   for( i = 0; i < argc; ++i )  
      printf( " %s", argv[i] );  
   printf( "\n" );  
}  
  
int compare( const void *arg1, const void *arg2 )  
{  
   /* Compare all of both strings: */  
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );  
}  
```  
  
```Output  
boy deserves every favor good  
```  
  
## <a name="see-also"></a>참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)