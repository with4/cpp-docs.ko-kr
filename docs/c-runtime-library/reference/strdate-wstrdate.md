---
title: "_strdate, _wstrdate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdate"
  - "_wstrdate"
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
  - "_tstrdate"
  - "wstrdate"
  - "_wstrdate"
  - "_strdate"
  - "strdate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strdate 함수"
  - "날짜, 복사"
  - "tstrdate 함수"
  - "_wstrdate 함수"
  - "wstrdate 함수"
  - "_strdate 함수"
  - "_tstrdate 함수"
  - "날짜 복사"
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _strdate, _wstrdate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

버퍼에 현재 시스템 날짜를 복사합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_strdate\_s, \_wstrdate\_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md)를 참조하십시오.  
  
## 구문  
  
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
  
#### 매개 변수  
 `datestr`  
 서식이 지정된 날짜 문자열을 포함 하는 버퍼에 대한 포인터입니다.  
  
## 반환 값  
 각 함수는 결과 문자열 `datestr` 에 대한 포인터를 반환합니다.  
  
## 설명  
 이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_strdate\_s, \_wstrdate\_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md) 를 참조하십시오.  가능한 더 안전한 함수를 사용 하는 것이 좋습니다.  
  
 `_strdate` 함수는 `datestr` 의해 지정된 버퍼에 대한 현재 시스템을 복사하거나, 서식이 지정된 `mm`\/`dd`\/`yy`, `mm` 이 달을 나타내는 두자리 숫자이고, `dd` 이 날을 나타내는 두개의 숫자이고, `yy` 이 연도의 마지막 두 숫자 입니다.  예를 들어, 문자열 `12/05/99` 는 1999 년 12 월 5 일을 나타냅니다.  버퍼에 적어도 9 바이트 보다 길어야 합니다.  
  
 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `datestr`이 `NULL` 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 `_wstrdate` 는 `_strdate` 의 와이드 문자 버전입니다. `_wstrdate` 인수와 반환 값은 와이드 문자 문자열입니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_tstrdate`|`_strdate`|`_strdate`|`_wstrdate`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
  **OS date: 04\/25\/03**   
## 해당 .NET Framework 항목  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)