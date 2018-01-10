---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
dev_langs: C++
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
caps.latest.revision: "35"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59c9d1f893dbc024a0645e70119d1069c3383ed8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="strnlen-strnlens-wcsnlen-wcsnlens-mbsnlen-mbsnlenl-mbstrnlen-mbstrnlenl"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
현재 로캘이나 전달된 로캘을 사용하여 문자열 길이를 가져옵니다. 이러한 함수는 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)의 더 안전한 버전입니다.  
  
> [!IMPORTANT]
>  `_mbsnlen`, `_mbsnlen_l`, `_mbstrnlen` 및 `_mbstrnlen_l`는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
size_t strnlen(  
   const char *str,  
   size_t numberOfElements   
);  
size_t strnlen_s(  
   const char *str,  
   size_t numberOfElements   
);  
size_t wcsnlen(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t wcsnlen_s(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen(  
   const unsigned char *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen_l(  
   const unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
size_t _mbstrnlen(  
   const char *str,  
   size_t numberOfElements  
);  
size_t _mbstrnlen_l(  
   const char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `str`  
 Null 종료 문자열입니다.  
  
 `numberOfElements`  
 문자열 버퍼의 크기입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 함수는 null 종결 문자를 제외하고 문자열에 있는 문자의 수를 반환합니다. 문자열의 첫 번째 `numberOfElements`바이트 내에(또는 `wcsnlen`의 와이드 문자) null 종결자가 없는 경우 `numberOfElements`는 오류 조건을 나타내기 위해 반환됩니다. null로 끝나는 문자열의 길이는 `numberOfElements`보다 확실히 짧습니다.  
  
 문자열에 잘못된 멀티바이트 문자가 있는 경우 `_mbstrnlen` 및 `_mbstrnlen_l`은 -1을 반환합니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  `strnlen`은 `strlen`을 대체하지 않습니다. `strnlen`은 네트워크 패킷과 같은 알려진 버퍼 크기로 들어오는 신뢰할 수 없는 데이터의 크기를 계산하는 데에만 사용할 수 있습니다. `strnlen`은 길이를 계산하지만 문자열이 종료되지 않은 경우 버퍼의 끝까지 진행하지 않습니다. 다른 상황에서는 `strlen`을 사용합니다. `wcsnlen`, `_mbsnlen` 및 `_mbstrnlen`에도 동일하게 적용됩니다.  
  
 이러한 각 함수는 null 종결 문자를 제외하고 `str`에 있는 문자의 수를 반환합니다. 그러나 `strnlen` 및 `strnlen_s`는 싱글바이트 문자열로 문자열을 해석하므로 문자열에 멀티바이트 문자가 포함되어 있더라도 반환 값은 항상 바이트 수와 동일합니다. `wcsnlen` 및 `wcsnlen_s`는 각각 `strnlen`과 `strnlen_s`의 와이드 문자 버전입니다.`wcsnlen` 및 `wcsnlen_s`의 인수는 와이드 문자열이고 문자 수는 와이드 문자 단위로 표시됩니다. 그렇지 않으면 `wcsnlen`과 `strnlen`은 `strnlen_s` 및 `wcsnlen_s`와 동일하게 작동합니다.  
  
 `strnlen``wcsnlen`, 및 `_mbsnlen` 매개 변수를 확인 하지 않습니다. `str`이 `NULL`인 경우 액세스 위반이 발생합니다.  
  
 `strnlen_s` 및 `wcsnlen_s`는 자신의 매개 변수에 대한 유효성을 검사합니다. `str`이 `NULL`인 경우 함수는 0을 반환합니다.  
  
 또한 `_mbstrnlen`은 자신의 매개 변수에 대한 유효성을 검사합니다. `str`이 `NULL`인 경우 또는 `numberOfElements`가 `INT_MAX`보다 큰 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명하는 대로 `_mbstrnlen`은 잘못된 매개 변수 예외를 생성합니다. 계속해서 실행하도록 허용한 경우 `_mbstrnlen`은 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsnlen`|`strnlen`|`strnlen`|`wcsnlen`|  
|`_tcscnlen`|`strnlen`|`_mbsnlen`|`wcsnlen`|  
|`_tcscnlen_l`|`strnlen`|`_mbsnlen_l`|`wcsnlen`|  
  
 `_mbsnlen` 및 `_mbstrnlen`은 멀티바이트 문자열의 멀티바이트 문자 수를 반환합니다. `_mbsnlen`은 현재 사용 중인 멀티바이트 코드 페이지 또는 전달된 로캘에 따라 멀티바이트 문자 시퀀스를 인식합니다. 멀티바이트 문자의 유효성에 대한 테스트는 수행하지 않습니다. `_mbstrnlen`은 멀티바이트 문자의 유효성을 테스트하고 멀티바이트 문자 시퀀스를 인식합니다. `_mbstrnlen`에 전달된 문자열에 잘못된 멀티바이트 문자가 포함된 경우 `errno`는 `EILSEQ`로 설정됩니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. 이러한 함수 버전은 `_l` 접미사가 없는 함수는 로캘 종속 동작에 현재 로캘을 사용하고 `_l` 접미사가 있는 함수는 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`strnlen`, `strnlen_s`|\<string.h>|  
|`wcsnlen`, `wcsnlen_s`|\<string.h> 또는 \<wchar.h>|  
|`_mbsnlen`, `_mbsnlen_l`|\<mbstring.h>|  
|`_mbstrnlen`, `_mbstrnlen_l`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```C  
// crt_strnlen.c  
  
#include <string.h>  
  
int main()  
{  
   // str1 is 82 characters long. str2 is 159 characters long   
  
   char* str1 = "The length of a string is the number of characters\n"  
               "excluding the terminating null.";  
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"  
                "than the maximum size specified, the maximum size is\n"  
                "returned rather than the actual size of the string.";  
   size_t len;  
   size_t maxsize = 100;  
  
   len = strnlen(str1, maxsize);  
   printf("%s\n Length: %d \n\n", str1, len);  
  
   len = strnlen(str2, maxsize);  
   printf("%s\n Length: %d \n", str2, len);  
}  
```  
  
```Output  
The length of a string is the number of characters  
excluding the terminating null.  
 Length: 82   
  
strnlen takes a maximum size. If the string is longer  
than the maximum size specified, the maximum size is  
returned rather than the actual size of the string.  
 Length: 100   
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)