---
title: "_mbclen, mblen, _mblen_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbclen
- mblen
- _mblen_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mblen
- ftclen
- _mbclen
- tclen
- _ftclen
- _tclen
- mbclen
dev_langs:
- C++
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 460de51d8f969f275ed392d293f90f517c168971
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="mbclen-mblen-mblenl"></a>_mbclen, mblen, _mblen_l
멀티바이트 문자의 길이를 가져오고 유효성을 확인합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t _mbclen(  
   const unsigned char *c   
);  
int mblen(  
   const char *mbstr,  
   size_t count   
);  
int _mblen_l(  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 멀티바이트 문자입니다.  
  
 `mbstr`  
 멀티바이트 문자 바이트 시퀀스의 주소입니다.  
  
 `count`  
 검사할 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `_mbclen`은 멀티바이트 문자 `c`의 길이가 1바이트인지 2바이트인지에 따라 1 또는 2를 반환합니다. `_mbclen`에 대해 반환되는 오류가 없습니다. `mbstr`이 `NULL`이 아닌 경우 `mblen`은 멀티바이트 문자의 길이(바이트)를 반환합니다. `mbstr`이 `NULL`이거나 와이드 문자 null 문자를 가리키는 경우 `mblen`은 0을 반환합니다. 경우 개체는 `mbstr` 가리키는 첫 번째 내에서 유효한 멀티 바이트 문자를 형성 하지 않습니다 `count` 문자인 `mblen` -1을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 `_mbclen` 함수는 멀티바이트 문자 `c`의 길이(바이트)를 반환합니다. `c`가 `_ismbblead`의 암시적 호출에 의해 결정된 멀티바이트 문자의 선행 바이트를 가리키지 않는 경우 `_mbclen`의 결과를 예측할 수 없습니다.  
  
 `mblen`은 `mbstr`이 유효한 멀티바이트 문자이고 코드 페이지와 관련된 멀티바이트 문자 유효성을 확인하는 경우 해당 문자의 길이(바이트)를 반환합니다. `mblen`은 `mbstr`에 포함된 `count` 이하 바이트를 검사하지만 `MB_CUR_MAX`를 초과하는 바이트는 검사하지 않습니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tclen`|매크로 또는 인라인 함수에 매핑|`_mbclen`|매크로 또는 인라인 함수에 매핑|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_mbclen`|\<mbstring.h>|  
|`mblen`|\<stdlib.h>|  
|`_mblen_l`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_mblen.c  
/* illustrates the behavior of the mblen function  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    int      i;  
    char    *pmbc = (char *)malloc( sizeof( char ) );  
    wchar_t  wc   = L'a';  
  
    printf( "Convert wide character to multibyte character:\n" );  
    wctomb_s( &i, pmbc, sizeof(char), wc );  
    printf( "  Characters converted: %u\n", i );  
    printf( "  Multibyte character: %x\n\n", *pmbc );  
  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );  
  
    pmbc = NULL;  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );  
}  
```  
  
## <a name="output"></a>출력  
  
```  
Convert wide character to multibyte character:  
  Characters converted: 1  
  Multibyte character: 61  
  
Length in bytes of multibyte character 61: 1  
Length in bytes of NULL multibyte character 0: 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbccpy, _mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)