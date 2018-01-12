---
title: "mbtowc, _mbtowc_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbtowc
- _mbtowc_l
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords: mbtowc
dev_langs: C++
helpviewer_keywords:
- mbtowc function
- _mbtowc_l function
- mbtowc_l function
ms.assetid: dfd1c8a7-e73a-4307-9353-53b70b45d4d1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52f2c1d3defb822f00095a24bfcc87bd07fc8cc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mbtowc-mbtowcl"></a>mbtowc, _mbtowc_l
멀티바이트 문자를 해당되는 와이드 문자로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int mbtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count   
);  
int _mbtowc_l(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *wchar*  
 와이드 문자의 주소입니다(`wchar_t` 형식).  
  
 `mbchar`  
 바이트 시퀀스(멀티바이트 문자)의 주소입니다.  
  
 *count*  
 검사할 바이트 수입니다.  
  
 *locale*  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 **mbchar**이 **NULL**이 아닌 경우 및 `mbchar`이 가리키는 개체가 유효한 멀티바이트 문자를 가리키는 경우 `mbtowc`는 멀티바이트 문자의 길이(바이트)를 반환합니다. `mbchar`이 **NULL**이거나 가리키는 개체가 와이드 문자 null 문자(L'\0')인 경우 함수는 0을 반환합니다. 경우 개체는 `mbchar` 가리키는 첫 번째 내에서 유효한 멀티 바이트 문자를 형성 하지 않습니다 *count* 문자를-1을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 `mbtowc` 함수는 `mbchar`이 **NULL**이 아닌 경우 `mbchar`이 가리키는 *count* 이하 바이트를 해당 와이드 문자로 변환합니다. `mbtowc`는 *wchar*이 **NULL**이 아닌 경우 *wchar*에 결과 와이드 문자를 저장합니다. `mbtowc`는 `MB_CUR_MAX` 바이트 이상을 검사하지 않습니다. `mbtowc`는 로캘 종속 동작의 현재 로캘을 사용하고 `_mbtowc_l`은 전달된 로캘을 사용한다는 점을 제외하고 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`mbtowc`|\<stdlib.h>|  
|**_mbtowc_l**|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예  
  
```  
// crt_mbtowc.c  
/* Illustrates the behavior of the mbtowc function  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    int      i;  
    char    *pmbc    = (char *)malloc( sizeof( char ) );  
    wchar_t  wc      = L'a';  
    wchar_t *pwcnull = NULL;  
    wchar_t *pwc     = (wchar_t *)malloc( sizeof( wchar_t ) );  
    printf( "Convert a wide character to multibyte character:\n" );  
    wctomb_s( &i, pmbc, sizeof(char), wc );  
    printf( "  Characters converted: %u\n", i );  
    printf( "  Multibyte character: %x\n\n", *pmbc );  
  
    printf( "Convert multibyte character back to a wide "  
            "character:\n" );  
    i = mbtowc( pwc, pmbc, MB_CUR_MAX );  
    printf( "  Bytes converted: %u\n", i );  
    printf( "  Wide character: %x\n\n", *pwc );  
    printf( "Attempt to convert when target is NULL\n" );  
    printf( "  returns the length of the multibyte character:\n" );  
    i = mbtowc( pwcnull, pmbc, MB_CUR_MAX );  
    printf( "  Length of multibyte character: %u\n\n", i );  
  
    printf( "Attempt to convert a NULL pointer to a" );  
    printf( " wide character:\n" );  
    pmbc = NULL;  
    i = mbtowc( pwc, pmbc, MB_CUR_MAX );  
    printf( "  Bytes converted: %u\n", i );  
}  
```  
  
## <a name="output"></a>출력  
  
```  
Convert a wide character to multibyte character:  
  Characters converted: 1  
  Multibyte character: 61  
  
Convert multibyte character back to a wide character:  
  Bytes converted: 1  
  Wide character: 61  
  
Attempt to convert when target is NULL  
  returns the length of the multibyte character:  
  Length of multibyte character: 1  
  
Attempt to convert a NULL pointer to a wide character:  
  Bytes converted: 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)