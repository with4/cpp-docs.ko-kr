---
title: _strdate, _wstrdate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdate
- _wstrdate
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tstrdate
- wstrdate
- _wstrdate
- _strdate
- strdate
dev_langs:
- C++
helpviewer_keywords:
- strdate function
- dates, copying
- tstrdate function
- _wstrdate function
- wstrdate function
- _strdate function
- _tstrdate function
- copying dates
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 108f846641f548f093719626ba08912c6b437f2f
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="strdate-wstrdate"></a>_strdate, _wstrdate
현재 시스템 날짜를 버퍼에 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *_strdate(  
   char *datestr   
);  
wchar_t *_wstrdate(  
   wchar_t *datestr   
);  
template <size_t size>  
char *_strdate(  
   char (&datestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrdate(  
   wchar_t (&datestr)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `datestr`  
 형식이 지정된 날짜 문자열을 포함하는 버퍼에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 각 함수는 결과 문자열 `datestr`에 대한 포인터를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md)를 참조하세요. 가능한 경우에는 항상 더 안전한 함수를 사용하는 것이 좋습니다.  
  
 `_strdate` 함수는 `mm`/`dd`/`yy` 형식의 `datestr`이 가리키는 버퍼에 현재 시스템 날짜를 복사합니다. 여기서 `mm`은 월을 나타내는 두 자리 숫자, `dd`는 일을 나타내는 두 자리 숫자, `yy`는 연도의 마지막 두 자리 숫자입니다. 예를 들어 `12/05/99` 문자열은 1999년 12월 5일을 나타냅니다. 버퍼는 9바이트 이상이어야 합니다.  
  
 `datestr`이 `NULL` 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수가 -1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 `_wstrdate`는 `_strdate`의 와이드 문자 버전이고, `_wstrdate`의 인수와 반환 값은 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.  
  
 C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate`|`_strdate`|`_strdate`|`_wstrdate`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_strdate`|\<time.h>|  
|`_wstrdate`|\<time.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// strdate.c  
// compile with: /W3  
#include <time.h>  
#include <stdio.h>  
int main()  
{  
    char tmpbuf[9];  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    printf( "OS date: %s\n", _strdate(tmpbuf) ); // C4996  
    // Note: _strdate is deprecated; consider using _strdate_s instead  
}  
```  
  
```Output  
OS date: 04/25/03  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
