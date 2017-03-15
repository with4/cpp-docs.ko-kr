---
title: "_strtime, _wstrtime | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstrtime"
  - "_strtime"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wstrtime"
  - "_strtime"
  - "wstrtime"
  - "strtime"
  - "_tstrtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtime 함수"
  - "_tstrtime 함수"
  - "_wstrtime 함수"
  - "버퍼에 시간 복사"
  - "strtime 함수"
  - "시간, 복사"
  - "tstrtime 함수"
  - "wstrtime 함수"
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _strtime, _wstrtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

버퍼에 시간을 복사 합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_strtime\_s, \_wstrtime\_s](../../c-runtime-library/reference/strtime-s-wstrtime-s.md)를 참조하십시오.  
  
## 구문  
  
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
  
#### 매개 변수  
 `timestr`  
 시간 문자열  
  
## 반환 값  
 결과 문자열 `timestr` 에 대한 포인터를 반환합니다.  
  
## 설명  
 `_strtime` 함수는 현재 로캘시간을 `timestr`*.* 으로 지정된 버퍼에 복사합니다. 24시간 표기법에서 `hh` 이 두개의 숫자 표현으로 시간은 `hh:mm:ss` 로 서식이 지정되고, `mm` 와 `ss` 는 각각 시간다음에 지난 분과 초로 표현됩니다.  예를 들어, 문자열 `18:23:44` 는 23분 44초 지난 오후 6시를 나타냅니다. 버퍼는 적어도 9바이트 이상이어야 합니다.  
  
 `_wstrtime` 는 `_strtime` 의 와이드 문자 버전입니다. `_wstrtime` 인수와 반환 값은 와이드 문자 문자열입니다.  이러한 기능은 동일하게 동작하지 않아 `timestr` 가 `NULL` 포인터이거나 `timestr` 의 형식이 잘못되었다면, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 것처럼 잘못된 매개변수 처리기가 호출됩니다.  만일 이 예외가 계속 된다면, 이 함수는 NULL을 반환하고 `timestr` 이 NULL이라면, `errno` 을 `EINVAL` 설정합니다. 만일 `timestr` 의 형식이 잘못되었다면 `errno` 을 `ERANGE` 로 설정합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_tstrtime`|`_strtime`|`_strtime`|`_wstrtime`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strtime`|\<time.h\>|  
|`_wstrtime`|\<time.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
  **현재 시간은 14:21:43입니다.**   
## 해당 .NET Framework 항목  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)