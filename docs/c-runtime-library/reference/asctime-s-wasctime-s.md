---
title: "asctime_s, _wasctime_s | Microsoft Docs"
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
  - "_wasctime_s"
  - "asctime_s"
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
  - "asctime_s"
  - "_wasctime_s"
  - "_tasctime_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tasctime_s 함수"
  - "_wasctime_s 함수"
  - "asctime_s 함수"
  - "tasctime_s 함수"
  - "시간 구조체 변환"
  - "시간, 변환"
  - "wasctime_s 함수"
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asctime_s, _wasctime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`tm` 시간 구조를 문자 문자열로 변환합니다.  이 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md) 버전입니다.  
  
## 구문  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### 매개 변수  
 `buffer`  
 \[out\] 문자 문자열 결과를 저장 하는 버퍼에 대한 포인터입니다.  이 함수는 `numberOfElements` 가 지정한 크기를 사용하는 올바른 메모리  포인터를 가정합니다.  
  
 `numberOfElements`  
 \[in\] 결과를 저장 하는 데 사용 되는 버퍼의 크기입니다.  
  
 `_tm`  
 \[in\] 시간\/날짜 구조체  이 함수는 유효한 `struct` `tm` 개체에 대해 포인터를 가정합니다.  
  
## 반환 값  
 성공 하면 0이 됩니다.  검사에 실패할 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  실행을 계속할 수 있는 경우 반환 값은 오류 코드입니다.  오류 코드는 ERRNO.H에서 정의 됩니다.  자세한 내용은 [errno 상수](../../c-runtime-library/errno-constants.md)을 참조하십시오.  각 오류 조건에 대해 반환 되는 실제 오류 코드는 다음 표에 나와 있습니다.  
  
### 오류 조건  
  
|`buffer`|`numberOfElements`|`tm`|반환|`buffer` 의 값입니다.|  
|--------------|------------------------|----------|--------|----------------------|  
|`NULL`|임의|임의|`EINVAL`|수정 되지 않음|  
|`NULL` 이 아닙니댜\(유효한 메모리를 가르킵니다\)|0|임의|`EINVAL`|수정 되지 않음|  
|`NULL`이 아닙니다.|0\< size \< 26|임의|`EINVAL`|빈 문자열|  
|`NULL`이 아닙니다.|\>\= 26|`NULL`|`EINVAL`|빈 문자열|  
|`NULL`이 아닙니다.|\>\= 26|시간의 구성요소에 대해 잘못 된 시간 구조 또는 범위를 벗어난 값입니다.|`EINVAL`|빈 문자열|  
  
> [!NOTE]
>  `wasctime_s` 에 대한 오류 조건은 단어에서 크기 제약이 측정 되는 예외를 사용하는 `asctime_s` 와 유사합니다.  
  
## 설명  
 `asctime` 함수는 구조체로 저장 된 시간을 문자 문자열로 변환합니다.  `_tm` 값은 종종 `gmtime` 또는 `localtime` 를 호출함으로서 얻어집니다.  TIME.H 에 정의된 두 함수는 `tm` 구조체를 작성하기 위해 사용 됩니다.  
  
|timeptr 멤버|값|  
|----------------|-------|  
|`tm_hour`|Hours since midnight \(0–23\)|  
|`tm_isdst`|양의 경우 일광 절약 시간제를 적용 합니다. 일광 절약 시간제가 효과가 없으면 0을 반환합니다. 일광 절약 시간을 알 수 없으면 음수를 반환합니다.  C 런타임 라이브러리는 일광 절약 시간제\(DST\)의 계산을 실행하는데 미국의 규칙을 사용한다고 가정합니다.|  
|`tm_mday`|Day of month \(1–31\)|  
|`tm_min`|Minutes after hour \(0–59\)|  
|`tm_mon`|Month \(0–11; January \= 0\)|  
|`tm_sec`|Seconds after minute \(0–59\)|  
|`tm_wday`|Day of week \(0–6; Sunday \= 0\)|  
|`tm_yday`|Day of year \(0–365; January 1 \= 0\)|  
|`tm_year`|Year \(current year minus 1900\)|  
  
 변환 된 문자열은 현지 표준 시간대 설정에 따라 조정할 수 있습니다.  현지 시간 구성에 대한 정보에 대한 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md), [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), and [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) 함수와 시간대 환경 및 전역 변수를 정의하는 방법에 대한 정보에 대한 [\_tzset](../../c-runtime-library/reference/tzset.md) 함수를 참조하십시오.  
  
 `asctime_s` 가 생성한 문자 결과를 정확히 26문자를 포함하고 서식 `Wed Jan 02 02:03:55 1980\n\0` 을 가집니다.  24 시간제를 사용 합니다.  모든 필드 너비가 일정합니다.  줄 바꿈 문자 및 null 문자가 문자열의 마지막 두 자리를 차지 합니다.  두 번째 매개 변수로 전달 된 값이 최소한 커야 합니다.  적은 경우 , 오류 코드 `EINVAL` 가 반환됩니다.  
  
 `_wasctime_s` 는 `asctime_s` 의 와이드 문자 버전입니다.  `_wasctime_s` 및 `asctime_s` 는 동일하게 작동합니다.  
  
### Generic\-Text Routine Mapping  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 C\+\+에서는 이러한 함수를 사용하는 것은 템플릿 오버로드에 의해 단순화됩니다; 오버로드는 자동으로 버퍼의 길이를 추정할수 있고, 크기 인수를 지정할 필요를 없앱니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`asctime_s`|\<time.h\>|  
|`_wasctime_s`|\<time.h\> or \<wchar.h\>|  
  
## 보안  
 버퍼 포인터가 `NULL` 이 아니고 포인터가 유효한 버퍼를 가르키지 않는 경우, 함수는 위치가 어디든 덮어씁니다.  이 것은 또한 액세스 위반을 발생할 수 있습니다.  
  
 크기 인수가 실제 버퍼의 크기보다 큰 경우 [buffer overrun](http://msdn.microsoft.com/library/windows/desktop/ms717795) 가 발생할 수 있습니다.  
  
## 예제  
 이 프로그램은 `asctime_s` 함수를 사용하여 시스템 시간을 구조체 `newtime` 로 변환하고 출력에 대해 문자열 서식으로 변환하는 long 정수`aclock`에 배치 합니다.  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
  **Current date and time: Wed May 14 15:30:17 2003**   
## 해당 .NET Framework 항목  
  
-   <xref:System.DateTime.ToLongDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToLongTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortDateString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortTimeString%2A?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToString%2A?displayProperty=fullName>  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)