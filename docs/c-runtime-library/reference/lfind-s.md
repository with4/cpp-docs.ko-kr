---
title: "_lfind_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lfind_s
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
- lfind_s
- _lfind_s
dev_langs: C++
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bff33c66ebe8bdb2b5eb497aad2e3a11bc04a76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="lfinds"></a>_lfind_s
지정된 키에 대해 선형 검색을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_lfind](../../c-runtime-library/reference/lfind.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *_lfind_s(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색 데이터의 기준에 대한 포인터입니다.  
  
 `num`  
 배열 요소의 수입니다.  
  
 `size`  
 배열 요소의 크기(바이트)입니다.  
  
 `compare`  
 비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수는 `context` 포인터입니다. 두 번째 매개 변수는 검색할 키에 대한 포인터입니다. 세 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.  
  
 `context`  
 비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 키가 있으면 `_lfind_s`는 `key`와 일치하는 `base`에서 배열의 요소에 대한 포인터를 반환합니다. 키가 없으면 `_lfind_s`는 `NULL`을 반환합니다.  
  
 함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|key|base|compare|num|size|errno|  
|---------|----------|-------------|---------|----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|!= 0|any|`EINVAL`|  
|any|any|any|any|0|`EINVAL`|  
|any|any|`NULL`|an|모두|`EINVAL`|  
  
## <a name="remarks"></a>설명  
 `_lfind_s` 함수는 각각 `width` 바이트인 `num` 요소의 배열에서 `key` 값에 대해 선형 검색을 수행합니다. `bsearch_s`와 달리 `_lfind_s`에서는 배열을 정렬할 필요가 없습니다. `base` 인수는 검색할 배열의 밑에 대한 포인터입니다. `compare` 인수는 두 배열 요소를 비교하여 해당 관계를 지정하는 값을 반환하는 사용자가 제공한 루틴에 대한 포인터입니다. `_lfind_s`는 검색 중에 `compare` 루틴을 한 번 이상 호출하며 각 호출에서 `context` 포인터 및 두 배열 요소에 대한 포인터를 전달합니다. `compare` 루틴은 요소를 비교한 다음 0이 아닌 값(요소가 다르다는 의미) 또는 0(요소가 동일하다는 의미)을 반환합니다.  
  
 `_lfind_s`는 비교 함수의 인수에 대한 `context` 포인터와 함수의 매개 변수 목록이 추가된다는 점을 제외하면 `_lfind`와 유사합니다. `context` 포인터는 검색된 데이터 구조가 개체의 일부이며 `compare` 함수가 개체의 멤버에 액세스해야 하는 경우에 유용할 수 있습니다. `compare` 함수는 void 포인터를 적절한 개체 형식으로 캐스팅하고 해당 개체의 멤버에 액세스할 수 있습니다. `context` 매개 변수를 추가하면 정적 변수를 사용하여 `compare` 함수에 데이터를 제공할 경우 발생하는 재진입 버그를 추가 컨텍스트로 방지할 수 있으므로 `_lfind_s`의 보안이 강화됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_lfind_s`|\<search.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_lfind_s.cpp  
// This program uses _lfind_s to search a string array,  
// passing a locale as the context.  
// compile with: /EHsc  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char *s1 = *(char**)str1;  
    char *s2 = *(char**)str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
void find_it( char *key, char *array[], unsigned int num, locale &loc )  
{  
   char **result = (char **)_lfind_s( &key, array,   
                      &num, sizeof(char *), compare, &loc );  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "%s not found\n", key );  
}  
  
int main( )  
{  
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );  
}  
```  
  
```Output  
weit found  
```  
  
## <a name="see-also"></a>참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort_s](../../c-runtime-library/reference/qsort-s.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)