---
title: "bsearch_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: bsearch_s
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
f1_keywords: bsearch_s
dev_langs: C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 19d60e16ee896049318d8722b59ba124aad67a50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bsearchs"></a>bsearch_s
정렬된 배열의 이진 검색을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [bsearch](../../c-runtime-library/reference/bsearch.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *bsearch_s(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),  
   void * context  
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
 두 요소를 비교하는 콜백 함수입니다. 첫 번째 인수는 `context` 포인터입니다. 두 번째 인수는 검색 `key` 에 대한 포인터입니다. 세 번째 인수는 `key`와 비교할 배열 요소에 대한 포인터입니다.  
  
 `context`  
 비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `bsearch_s`는 `base`가 가리키는 배열의 `key` 발생에 대한 포인터를 반환합니다. `key` 가 없을 경우 함수는 `NULL`을 반환합니다. 배열이 오름차순 정렬이 아니거나 동일한 키를 가진 중복 레코드를 포함하는 경우에는 결과를 예측할 수 없습니다.  
  
 함수에 잘못된 매개 변수를 전달하면 [Parameter Validation](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
### <a name="error-conditions"></a>오류 조건  
  
|||||||  
|-|-|-|-|-|-|  
|`key`|`base`|`compare`|`num`|`width`|`errno`|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|!= 0|any|`EINVAL`|  
|any|any|any|any|= 0|`EINVAL`|  
|any|any|`NULL`|an|모두|`EINVAL`|  
  
## <a name="remarks"></a>설명  
 `bsearch_s` 함수는 각각 크기가 `num` 바이트인 `width` 요소의 정렬된 배열에 대해 이진 검색을 수행합니다. `base` 값은 검색할 배열 기준에 대한 포인터이고 `key` 는 검색되는 값입니다. `compare` 매개 변수는 요청된 키를 배열 요소와 비교하고 해당 관계를 지정하는 다음 값 중 하나를 반환하는 사용자 제공 루틴에 대한 포인터입니다.  
  
|`compare` 루틴에서 반환된 값|설명|  
|-----------------------------------------|-----------------|  
|\< 0|키가 배열 요소보다 작습니다.|  
|0|키가 배열 요소와 같습니다.|  
|> 0|키가 배열 요소보다 큽니다.|  
  
 `context` 포인터는 검색된 데이터 구조가 개체의 일부이며 비교 함수가 개체의 멤버에 액세스해야 하는 경우에 유용할 수 있습니다. `compare` 함수는 void 포인터를 적절한 개체 형식으로 캐스팅하고 해당 개체의 멤버에 액세스할 수 있습니다. `context` 매개 변수를 추가하면 정적 변수를 사용하여 `bsearch_s` 함수에 데이터를 제공할 경우 발생하는 재진입 버그를 추가 컨텍스트로 방지할 수 있으므로 `compare` 보안이 강화됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`bsearch_s`|\<stdlib.h> 및 \<search.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 이 프로그램은 [qsort_s](../../c-runtime-library/reference/qsort-s.md)를 사용하여 문자열 배열을 정렬한 다음 bsearch_s를 사용하여 "cat" 단어를 찾습니다.  
  
```  
// crt_bsearch_s.cpp  
// This program uses bsearch_s to search a string array,  
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
#define ENGLISH_LOCALE "English_US.850"  
#endif  
  
#ifdef CODEPAGE_1252  
#define ENGLISH_LOCALE "English_US.1252"  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, char **str1, char **str2)  
{  
    char *s1 = *str1;  
    char *s2 = *str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
  
   char *key = "cat";  
   char **result;  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort_s( arr,  
            sizeof(arr)/sizeof(arr[0]),  
            sizeof( char * ),  
            (int (*)(void*, const void*, const void*))compare,  
            &locale(ENGLISH_LOCALE) );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch_s( &key,  
                                arr,  
                                sizeof(arr)/sizeof(arr[0]),  
                                sizeof( char * ),  
                                (int (*)(void*, const void*, const void*))compare,  
                                &locale(ENGLISH_LOCALE) );  
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