---
title: "bsearch | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: bsearch
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
f1_keywords: bsearch
dev_langs: C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1db24ea4be15c4111b94a28323903dd3f2c3ed7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bsearch"></a>bsearch
정렬된 배열의 이진 검색을 수행합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색 데이터 기준에 대한 포인터입니다.  
  
 `num`  
 요소의 수입니다.  
  
 `width`  
 요소의 너비입니다.  
  
 `compare`  
 두 요소를 비교하는 콜백 함수입니다. 첫 번째 요소는 검색 키에 대한 포인터이고 두 번째 요소는 키와 비교할 배열 요소에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `bsearch`는 `base`가 가리키는 배열의 `key` 발생에 대한 포인터를 반환합니다. `key` 가 없을 경우 함수는 `NULL`을 반환합니다. 배열이 오름차순 정렬이 아니거나 동일한 키를 가진 중복 레코드를 포함하는 경우에는 결과를 예측할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 `bsearch` 함수는 각각 크기가 `num` 바이트인 `width` 요소의 정렬된 배열에 대해 이진 검색을 수행합니다. `base` 값은 검색할 배열 기준에 대한 포인터이고 `key` 는 검색되는 값입니다. `compare` 매개 변수는 요청된 키를 배열 요소와 비교하고 해당 관계를 지정하는 다음 값 중 하나를 반환하는 사용자 제공 루틴에 대한 포인터입니다.  
  
|`compare` 루틴에서 반환된 값|설명|  
|-----------------------------------------|-----------------|  
|\< 0|키가 배열 요소보다 작습니다.|  
|0|키가 배열 요소와 같습니다.|  
|> 0|키가 배열 요소보다 큽니다.|  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `compare`, `key` 또는 `num`이 `NULL`이거나, `base`가 `NULL`이고 *`num`이 0이 아니거나, `width`가 0이면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`bsearch`|\<stdlib.h> 및 \<search.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 이 프로그램은 qsort를 사용하여 문자열 배열을 정렬한 다음 bsearch를 사용하여 "cat" 단어를 찾습니다.  
  
```  
// crt_bsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( char **arg1, char **arg2 )  
{  
   /* Compare all of both strings: */  
   return _strcmpi( *arg1, *arg2 );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
   char **result;  
   char *key = "cat";  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const   
   void*, const void*))compare );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),  
                              sizeof( char * ), (int (*)(const void*, const void*))compare );  
   if( result )  
      printf( "\n%s found at %Fp\n", *result, result );  
   else  
      printf( "\nCat not found!\n" );  
}  
```  
  
```Output  
cat cow dog goat horse human pig rat  
cat found at 002F0F04  
```  
  
## <a name="see-also"></a>참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)