---
title: "_strtime_s, _wstrtime_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstrtime_s"
  - "_strtime_s"
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
  - "_wstrtime_s"
  - "strtime_s"
  - "wstrtime_s"
  - "_strtime_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtime_s 함수"
  - "_wstrtime_s 함수"
  - "버퍼에 시간 복사"
  - "strtime_s 함수"
  - "시간, 복사"
  - "wstrtime_s 함수"
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strtime_s, _wstrtime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

버퍼에 현재 시간을 복사 합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [\_strtime, \_wstrtime](../../c-runtime-library/reference/strtime-wstrtime.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _strtime_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrtime_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strtime_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrtime_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `buffer`  
 시간이 기록 될 때 최대 10 바이트 길이의 버퍼입니다.  
  
 \[in\] `numberOfElements`  
 버퍼의 크기입니다.  
  
## 반환 값  
 성공시 0입니다.  
  
 오류 조건이 발생 하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못 된 매개 변수 처리기를 호출합니다.  오류가 발생한 경우 반환 값은 오류 코드입니다.  오류 코드는 ERRNO.H의에 정의되어있습니다. 이 기능에 의해 생성 된 정확한 오류에 대해 다음 표를 참조하십시오.  오류 코드에 대한 자세한 정보는 [errno Constants](../../c-runtime-library/errno-constants.md) 를 참조하십시오.  
  
### 오류 조건  
  
|`buffer`|`numberOfElements`|반환|`buffer`의 내용입니다.|  
|--------------|------------------------|--------|----------------------|  
|`NULL`|모두|`EINVAL`|수정되지 않음|  
|`NULL` 이 아닙니다.\(유효한 버퍼에 대한 포인터\)|0|`EINVAL`|수정되지 않음|  
|`NULL` 이 아닙니다.\(유효한 버퍼에 대한 포인터\)|0 \< size \< 9|`EINVAL`|빈 문자열|  
|`NULL` 이 아닙니다.\(유효한 버퍼에 대한 포인터\)|Size \> 9|0|설명에 지정 된 형식인 현재 시간|  
  
## 보안 문제  
 `numberOfElements` 매개 변수가 9보다 큰 경우, 버퍼에 대해 NULL이 아닌 잘못된 값을 전달하는 것은 액세스 위반을 발생시킵니다.  
  
 버퍼의 실제 크기보다 큰 `numberOfElements` 에 대한 값의 전달은 버퍼 오버런을 발생시킵니다.  
  
## 설명  
 이러한 함수는 `_strtime` 및 `_wstrtime` 의 보다 안전한 버전을 제공합니다.  `_strtime_s` 함수는 현재 로캘시간을 `timestr`*.* 으로 지정된 버퍼에 복사합니다. 24시간 표기법에서 `hh` 이 두개의 숫자 표현으로 시간은 `hh:mm:ss` 로 서식이 지정되고, `mm` 와 `ss` 는 각각 시간다음에 지난 분과 초로 표현됩니다.  예를 들어, 문자열 `18:23:44` 는 23분 44초 지난 오후 6시를 나타냅니다. 버퍼는 최소 9바이트 이상이어야 합니다. 실제 크기는 두번째 매개 변수에 의해 지정 됩니다.  
  
 `_wstrtime` 는 `_strtime` 의 와이드 문자 버전입니다. `_wstrtime` 인수와 반환 값은 와이드 문자 문자열입니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑:  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tstrtime_s`|`_strtime_s`|`_strtime_s`|`_wstrtime_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strtime_s`|\<time.h\>|  
|`_wstrtime_s`|\<time.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// strtime_s.c  
  
#include <time.h>  
#include <stdio.h>  
  
int main()  
{  
    char tmpbuf[9];  
    errno_t err;  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    // Display operating system-style date and time.   
    err = _strtime_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
      exit(1);  
    }  
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );  
    err = _strdate_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );  
  
}  
```  
  
  **OS time:            14:37:49**  
**OS date:            04\/25\/03**   
## 해당 .NET Framework 항목  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)