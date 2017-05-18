---
title: _strtime, _wstrtime | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wstrtime
- _strtime
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
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
dev_langs:
- C++
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
caps.latest.revision: 22
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: d442d5d1d32fe7ab1a6dfe4e16e64b3dd994b73e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime
버퍼에 시간을 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strtime_s, _wstrtime_s](../../c-runtime-library/reference/strtime-s-wstrtime-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *_strtime(  
   char *timestr   
);  
wchar_t *_wstrtime(  
   wchar_t *timestr   
);  
template <size_t size>  
char *_strtime(  
   char (&timestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrtime(  
   wchar_t (&timestr)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `timestr`  
 시간 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 결과 문자열 `timestr`에 대한 포인터를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_strtime` 함수는 현재 현지 시간에서 가리키는 버퍼에 복사 `timestr`합니다. 시간 형식은 `hh:mm:ss`로 지정됩니다. 여기서 `hh`는 24시간 표기법의 시간을 나타내는 2자리 숫자, `mm`은 분을 나타내는 2자리 숫자, 그리고 `ss`는 초를 나타내는 2자리 숫자입니다. 예를 들어 문자열 `18:23:44`는 오후 6시 23분 44초를 나타냅니다. 버퍼는 9바이트 이상이어야 합니다.  
  
 `_wstrtime`는 `_strtime`의 와이드 문자 버전이고, `_wstrtime`의 인수와 반환 값은 와이드 문자 문자열입니다. 이러한 함수는 그 외의 경우에는 동일하게 동작합니다. `timestr`이 `NULL`이거나 `timestr`의 형식이 잘못된 경우에는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 예외가 계속되도록 허용되는 경우 이러한 함수는 NULL을 반환하며, `timestr`이 NULL이면 `errno`를 `EINVAL`로 설정하고 `timestr`의 형식이 잘못된 경우에는 `errno`를 `ERANGE`로 설정합니다.  
  
 C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrtime`|`_strtime`|`_strtime`|`_wstrtime`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_strtime`|\<time.h>|  
|`_wstrtime`|\<time.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_strtime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char tbuffer [9];  
   _strtime( tbuffer ); // C4996  
   // Note: _strtime is deprecated; consider using _strtime_s instead  
   printf( "The current time is %s \n", tbuffer );  
}  
```  
  
```Output  
The current time is 14:21:44  
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
