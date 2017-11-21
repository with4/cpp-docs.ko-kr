---
title: "_mbsnbcmp, _mbsnbcmp_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbcmp
- _mbsnbcmp_l
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
apitype: DLLExport
f1_keywords:
- mbsnbcmp
- tcsnbmp
- _mbsnbcmp_l
- mbsnbcmp_l
- _mbsnbcmp
dev_langs: C++
helpviewer_keywords:
- mbsnbcmp_l function
- mbsnbcmp function
- tcsncmp function
- _mbsnbcmp_l function
- _tcsncmp function
- _mbsnbcmp function
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 15546fc6c5eda56da53fd39581e6d101d014fa51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mbsnbcmp-mbsnbcmpl"></a>_mbsnbcmp, _mbsnbcmp_l
두 멀티바이트 문자열의 처음 `n`바이트를 비교합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _mbsnbcmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `string1, string2`  
 비교할 문자열입니다.  
  
 `count`  
 비교할 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 값은 `string1` 및 `string`의 부분 문자열 간의 서수 관계를 나타냅니다.  
  
|반환 값|설명|  
|------------------|-----------------|  
|< 0|`string1` 부분 문자열이 `string2` 부분 문자열보다 작습니다.|  
|0|`string1` 부분 문자열이 `string2` 부분 문자열과 같습니다.|  
|> 0|`string1` 부분 문자열이 `string2` 부분 문자열보다 큽니다.|  
  
 매개 변수 유효성 검사 오류 시 `_mbsnbcmp` 및 `_mbsnbcmp_l`은 \<string.h> 및 \<mbstring.h>에 정의된 `_NLSCMPERROR`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_mbsnbcmp` 함수는 `count` 및 `string1`의 처음 `string2`자까지를 비교한 다음 부분 문자열 간의 관계를 나타내는 값을 반환합니다. `_mbsnbcmp`는 대소문자를 구분하는 `_mbsnbicmp` 버전입니다. `_mbsnbcoll`과는 달리 `_mbsnbcmp`에는 로캘의 데이터 정렬 순서가 적용되지 않습니다. `_mbsnbcmp`는 현재 멀티바이트 [코드 페이지](../../c-runtime-library/code-pages.md)에 따라 멀티바이트 문자 시퀀스를 인식합니다.  
  
 `_mbsnbcmp`는 `_mbsncmp`와 비슷합니다. 단, `_mbsncmp`는 문자열을 바이트가 아닌 문자로 비교합니다.  
  
 출력 값에는 로캘의 `LC_CTYPE` 범주 설정이 적용됩니다. 이 설정은 멀티바이트 문자의 선행 바이트 및 후행 바이트를 지정합니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_mbsnbcmp` 함수는 이 로캘 종속 동작에 대해 현재 로캘을 사용합니다. `_mbsnbcmp_l` 함수는 `locale` 매개 변수를 대신 사용한다는 점을 제외하면 이 함수와 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `string1` 또는 `string2`가 null 포인터이면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이 함수는 `_NLSCMPERROR`를 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|---------------------------------------|--------------------|-----------------------|  
|`_tcsncmp`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcmp`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
|`_tcsncmp_l`|[strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|`_mbsnbcml`|[wcsncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_mbsnbcmp`|\<mbstring.h>|  
|`_mbsnbcmp_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_mbsnbcmp.c  
#include <mbstring.h>  
#include <stdio.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown fox jumps over the lazy dog";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
   printf( "Compare strings:\n          %s\n", string1 );  
   printf( "          %s\n\n", string2 );  
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );  
   result = _mbsncmp( string1, string2 , 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );  
   result = _mbsnicmp( string1, string2, 10 );  
   if( result > 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );  
   else if( result < 0 )  
      _mbscpy_s( tmp, sizeof(tmp), "less than" );  
   else  
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );  
   printf( "Result:   String 1 is %s string 2\n\n", tmp );  
}  
```  
  
## <a name="output"></a>출력  
  
```  
Compare strings:  
          The quick brown dog jumps over the lazy fox  
          The QUICK brown fox jumps over the lazy dog  
  
Function: _mbsnbcmp (first 10 characters only)  
Result:   String 1 is greater than string 2  
  
Function: _mbsnicmp _mbsnicmp (first 10 characters only)  
Result:   String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbicmp, _mbsnbicmp_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)