---
title: "_lfind | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lfind
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lfind
- _lfind
dev_langs: C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f883aa9f17c8272335a91ebf333e050888be8257
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="lfind"></a>_lfind
지정된 키에 대해 선형 검색을 수행합니다. 이 함수의 보다 안전한 버전을 사용할 수 있습니다. [_lfind_s](../../c-runtime-library/reference/lfind-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색 데이터의 기준에 대한 포인터입니다.  
  
 `num`  
 배열 요소의 수입니다.  
  
 `width`  
 배열 요소의 너비입니다.  
  
 `compare`  
 비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수는 검색할 키에 대한 포인터입니다. 두 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 키가 있으면 `_lfind`는 `key`와 일치하는 `base`에서 배열의 요소에 대한 포인터를 반환합니다. 키가 없으면 `_lfind`는 `NULL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_lfind` 함수는 각각 `width` 바이트인 `num` 요소의 배열에서 `key` 값에 대해 선형 검색을 수행합니다. `bsearch`와 달리 `_lfind`에서는 배열을 정렬할 필요가 없습니다. `base` 인수는 검색할 배열의 밑에 대한 포인터입니다. `compare` 인수는 두 배열 요소를 비교하여 해당 관계를 지정하는 값을 반환하는 사용자가 제공한 루틴에 대한 포인터입니다. `_lfind`는 검색 중에 `compare` 루틴을 한 번 이상 호출하며 각 호출에서 두 배열 요소에 대한 포인터를 전달합니다. `compare` 루틴은 요소를 비교한 다음 0이 아닌 값(요소가 다르다는 의미) 또는 0(요소가 동일하다는 의미)을 반환합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `compare`, `key` 또는 `num`이 `NULL`인 경우, `base`가 NULL이고 *`num`이 0이 아닌 경우 또는 `width`가 0보다 작은 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_lfind`|\<search.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_lfind.c  
// This program uses _lfind to search a string array  
// for an occurrence of "hello".  
  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
  
int main( )  
{  
   char *arr[] = {"Hi", "Hello", "Bye"};  
   int n = sizeof(arr) / sizeof(char*);  
   char **result;  
   char *key = "hello";  
  
   result = (char **)_lfind( &key, arr,   
                      &n, sizeof(char *), compare );  
  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "hello not found!\n" );  
}  
```  
  
```Output  
Hello found  
```  
  
## <a name="see-also"></a>참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)