---
title: "_lsearch | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _lsearch
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
- _lsearch
- lsearch
dev_langs:
- C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb4cb64b9287de11a894a8ca7c7cdd4490fcc446
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="lsearch"></a>_lsearch
값에 대한 선형 검색을 수행합니다. 찾을 수 없는 경우 목록의 끝에 추가합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색할 배열의 기준에 대한 포인터입니다.  
  
 `num`  
 요소의 수입니다.  
  
 `width`  
 각 배열 요소의 너비입니다.  
  
 `compare`  
 비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수는 검색할 키에 대한 포인터입니다. 두 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 키가 있으면 `_lsearch`는 `key`와 일치하는 `base`에서 배열의 요소에 대한 포인터를 반환합니다. 키가 없는 경우 `_lsearch`는 배열의 끝에서 새로 추가된 항목에 대한 포인터를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_lsearch` 함수는 각각 `width` 바이트인 `num` 요소의 배열에서 `key` 값에 대해 선형 검색을 수행합니다. `bsearch`와 달리 `_lsearch`에서는 배열을 정렬할 필요가 없습니다. `key`가 없는 경우 `_lsearch`는 배열의 끝에 추가하고 `num`을 늘립니다.  
  
 `compare` 인수는 두 배열 요소를 비교하여 해당 관계를 지정하는 값을 반환하는 사용자가 제공한 루틴에 대한 포인터입니다. `_lsearch`는 검색 중에 `compare` 루틴을 한 번 이상 호출하며 각 호출에서 두 배열 요소에 대한 포인터를 전달합니다. `compare`는 요소를 비교하고 0이 아닌 값(요소가 다르다는 의미) 또는 0(요소가 동일하다는 의미)을 반환합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `compare`, `key` 또는 `num`이 `NULL`인 경우, `base`가 NULL이고 *`num`이 0이 아닌 경우 또는 `width`가 0보다 작은 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_lsearch`|\<search.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_lsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main(void)  
{  
   char * wordlist[4] = { "hello", "thanks", "bye" };  
                            // leave room to grow...  
   int n = 3;  
   char **result;  
   char *key = "extra";  
   int i;  
  
   printf( "wordlist before _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
  
   result = (char **)_lsearch( &key, wordlist,   
                      &n, sizeof(char *), compare );  
  
   printf( "wordlist after _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
}  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
```  
  
```Output  
wordlist before _lsearch: hello thanks bye  
wordlist after _lsearch: hello thanks bye extra  
```  
  
## <a name="see-also"></a>참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)