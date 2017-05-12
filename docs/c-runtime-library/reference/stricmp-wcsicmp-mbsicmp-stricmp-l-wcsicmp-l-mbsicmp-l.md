---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
dev_langs:
- C++
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3502f864ce5450e86acd673d2911ed7f5393e5fe
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
대소문자를 구분하지 않는 문자열 비교를 수행합니다.  
  
> [!IMPORTANT]
> Windows 런타임에서 실행되는 응용 프로그램에서는  `_mbsicmp` 및 `_mbsicmp_l`을 사용할 수는 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _stricmp(  
   const char *string1,  
   const char *string2   
);  
int _wcsicmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricmp_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `string1, string2`  
 비교할 Null 종료 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 값은 `string1`에 대한 `string2`의 관계를 다음과 같이 나타냅니다.  
  
|반환 값|설명|  
|------------------|-----------------|  
|< 0|`string1`이 `string2`보다 짧음|  
|0|`string1` = `string2`|  
|> 0|`string1` > `string2`|  
  
 오류 발생 시 `_mbsicmp`는 \<string.h> 및 \<mbstring.h>에 정의된 `_NLSCMPERROR`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_stricmp` 함수는 각 문자를 소문자로 변환한 다음 `string1` 및 `string2`를 서수로 비교하여 해당 관계를 나타내는 값을 반환합니다. `_stricmp` 비교에는 대문자와 소문자를 결정하는 `_stricoll`만 적용된다는 점에서 `_stricmp`와 `LC_CTYPE`은 서로 다릅니다. `_stricoll` 함수는 로캘의 `LC_CTYPE` 및 `LC_COLLATE` 범주 둘 다에 따라 문자열을 비교합니다. 여기에는 대소문자 및 데이터 정렬 순서가 모두 포함됩니다. `LC_COLLATE` 범주에 대한 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 및 [로캘 범주](../../c-runtime-library/locale-categories.md)를 참조하세요. `_l` 접미사가 없는 이러한 함수의 버전은 로캘 종속 동작에 현재 로캘을 사용합니다. 접미사가 있는 버전은 전달된 로캘을 사용한다는 점만 제외하면 동일합니다. 로캘이 설정되지 않은 경우에는 C 로캘이 사용됩니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
> [!NOTE]
>  `_stricmp`는 `_strcmpi`와 같습니다. 이 두 항목은 서로 바꿔 사용할 수 있지만 기본적으로 사용되는 표준은 `_stricmp`입니다.  
  
 `_strcmpi` 함수는 `_stricmp`와 같으며 이전 버전과의 호환성을 위해서만 제공됩니다.  
  
 `_stricmp`는 소문자 비교를 수행하므로 예기치 않은 동작이 발생할 수 있습니다.  
  
 `_stricmp`가 수행하는 대소문자 변환이 비교 결과에 영향을 주는 경우를 살펴보기 위해 JOHNSTON과 JOHN_HENRY라는 두 문자열이 있다고 가정해 보겠습니다. JOHN_HENRY 문자열은 "_"의 ASCII 값이 소문자 S보다 작기 때문에 JOHNSTON보다 작은 것으로 간주됩니다. 실제로 ASCII 값이 91~96인 문자는 모든 문자보다 작은 것으로 간주됩니다.  
  
 `_stricmp` 대신 [strcmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md) 함수를 사용하는 경우에는 JOHN_HENRY가 JOHNSTON보다 큽니다.  
  
 `_wcsicmp` 및 `_mbsicmp`는 `_stricmp`의 와이드 문자 및 멀티바이트 문자 버전입니다. `_wcsicmp`의 인수 및 반환 값은 와이드 문자열이며 `_mbsicmp`의 인수와 반환 값은 멀티바이트 문자열입니다. `_mbsicmp`는 현재 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하며 오류 발생 시 `_NLSCMPERROR`를 반환합니다. 자세한 내용은 [코드 페이지](../../c-runtime-library/code-pages.md) 참조하세요. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 `_wcsicmp`는 인수를 비교하기 전에 소문자로 변환하지 않는다는 점을 제외하면 `wcscmp` 및 `wcscmp`는 동일하게 작동합니다. `_mbsicmp`는 인수를 비교하기 전에 소문자로 변환하지 않는다는 점을 제외하면 `_mbscmp` 및 `_mbscmp`는 동일하게 작동합니다.  
  
 라틴 1 문자를 사용하려면 `_wcsicmp`에 대해 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 호출해야 합니다. 기본적으로는 C 로캘이 적용되므로 예를 들어 ä와 Ä는 비교 시 같은 항목으로 간주되지 않습니다. `setlocale`를 호출하기 전에 C 이외의 로캘로 `_wcsicmp`을 호출합니다. 다음 샘플에서는 `_wcsicmp`가 로캘을 구분하는 방식을 보여 줍니다.  
  
```  
// crt_stricmp_locale.c  
#include <string.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main() {  
   setlocale(LC_ALL,"C");   // in effect by default  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails  
   setlocale(LC_ALL,"");  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds  
}  
```  
  
 또는 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)을 호출하고 반환되는 로캘 개체를 매개 변수로 `_wcsicmp_l`에 전달합니다.  
  
 이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `string1` 또는 `string2`가 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우, 이러한 함수는 `_NLSCMPERROR`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsicmp`|`_stricmp`|`_mbsicmp`|`_wcsicmp`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_stricmp`, `_stricmp_l`|\<string.h>|  
|`_wcsicmp`, `_wcsicmp_l`|\<string.h> 또는 \<wchar.h>|  
|`_mbsicmp`, `_mbsicmp_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_stricmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
   The quick brown dog jumps over the lazy fox  
   The QUICK brown dog jumps over the lazy fox  
  
   strcmp:   String 1 is greater than string 2  
   _stricmp:  String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [_memicmp, _memicmp_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
