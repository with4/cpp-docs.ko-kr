---
title: _lfind | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _lfind
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
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f60ea8dd05f9dffd6778c001e3f150f95744ae2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lfind"></a>_lfind

지정된 키에 대해 선형 검색을 수행합니다. 이 함수의 보다 안전한 버전을 사용할 수 있습니다. [_lfind_s](lfind-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void *_lfind(
   const void *key,
   const void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 개체입니다.

*base*<br/>
검색 데이터의 기준에 대한 포인터입니다.

*번호*<br/>
배열 요소의 수입니다.

*width*<br/>
배열 요소의 너비입니다.

*compare*<br/>
비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수는 검색할 키에 대한 포인터입니다. 두 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

키가 있으면 **_lfind** 배열의 요소에 대 한 포인터를 반환 *기본* 일치 하는 *키*합니다. 키가 없으면 **_lfind** 반환 **NULL**합니다.

## <a name="remarks"></a>설명

**_lfind** 함수 값에 대 한 선형 검색을 수행 *키* 배열을 *번호* 의 각 요소 *너비* 바이트입니다. 와 달리 **bsearch**, **_lfind** 정렬할 배열 필요 하지 않습니다. *기본* 인수는 검색할 배열의 기준에 대 한 포인터입니다. *비교* 인수는 두 개의 배열 요소를 비교 하 고 다음의 관계를 지정 하는 값을 반환 하는 사용자 제공 루틴에 대 한 포인터입니다. **_lfind** 호출은 *비교* 일상적인 한 번 이상 호출할 때마다 두 배열 요소에 포인터를 전달 검색 중. *비교* 루틴에서 요소를 비교 하 고 (요소는 서로 다른 의미) 0이 아닌 값을 반환 해야 또는 0 (요소는 동일).

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *비교*, *키* 또는 *번호* 은 **NULL**, if 또는 *기본* null 및 **번호*  이 값은 0 이거나 *너비* 작으면 0 보다는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수가 반환 하 고 **NULL**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_lfind**|\<search.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
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

## <a name="see-also"></a>참고자료

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
