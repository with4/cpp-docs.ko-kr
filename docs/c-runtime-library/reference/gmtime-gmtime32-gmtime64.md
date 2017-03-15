---
title: "gmtime, _gmtime32, _gmtime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gmtime32"
  - "gmtime"
  - "_gmtime64"
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
  - "gmtime"
  - "_gmtime32"
  - "_gmtime64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_gmtime32 함수"
  - "_gmtime64 함수"
  - "gmtime 함수"
  - "gmtime32 함수"
  - "gmtime64 함수"
  - "시간 함수"
  - "시간 구조체 변환"
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# gmtime, _gmtime32, _gmtime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구조에는 시간 값을 변환합니다. 이러한 함수의 더 안전한 버전은 사용할 수 있습니다. 참조 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)합니다.  
  
## 구문  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### 매개 변수  
 `timer`  
 저장 된 시간에 대 한 포인터입니다. 자정 이후 경과 된 초 시간 표현 됩니다 \(00: 00:00\), 1970 년 1 월 1 일 협정 세계시 \(UTC\)입니다.  
  
## 반환 값  
 형식의 구조에 대 한 포인터 [tm](../../c-runtime-library/standard-types.md)합니다. 계산 된 값을 유지 하는 반환 된 구조체의 필드는 `timer` utc에서 대신 현지 시간으로 인수입니다. 각 구조 필드의 형식입니다 `int`, 다음과 같이 합니다.  
  
 `tm_sec`  
 분 후 시간 \(초\) \(0\-59\).  
  
 `tm_min`  
 1 시간 후 분 \(0\-59\).  
  
 `tm_hour`  
 자정 이후의 시간 \(0\-23\).  
  
 `tm_mday`  
 날짜 \(1\-31\)입니다.  
  
 `tm_mon`  
 월 \(0\-11; 1 월 \= 0\).  
  
 `tm_year`  
 연도 \(1900\-현재 년\)입니다.  
  
 `tm_wday`  
 요일 \(0\-6; 일요일 \= 0\).  
  
 `tm_yday`  
 연간 일자 \(0\-365; 1 월 1 일 \= 0\).  
  
 `tm_isdst`  
 항상 0에 대 한 `gmtime`합니다.  
  
 32 비트 및 64 비트 버전 모두 `gmtime`, `mktime`, `mkgmtime`, 및 `localtime` 하나의 공통을 사용 하 여 모든 `tm` 변환을 위해 스레드당 구조입니다. 이러한 함수 중 하나를 호출할 때마다 모든 이전 호출의 결과 삭제합니다. 경우 `timer` 1970 년 1 월 1 일 이전의 날짜를 나타내는 `gmtime` 반환 `NULL`합니다. 반환되는 오류가 없습니다.  
  
 `_gmtime64`, 를 사용 하 여 `__time64_t` 구조, 23시 59분: 59 까지의 3000 년 12 월 31 일 UTC 표시 해야 하는 날짜를 사용 하면 반면 `_gmtime32` 만 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다. 자정 1970 년 1 월 1 일에 두 함수에 대 한 날짜 범위의 하한값입니다.  
  
 `gmtime` 계산 되는 인라인 함수 이며 `_gmtime64`, 를 및 `time_t` 같습니다 `__time64_t` 하지 않는 한 `_USE_32BIT_TIME_T` 정의 됩니다. 해석 하는 컴파일러를 강제 수행 해야 `time_t` 이전 32 비트와 `time_t`, 를 정의할 수 있습니다 `_USE_32BIT_TIME_T`, 하지만 이렇게 하면 `gmtime` 인라인 되도록 `_gmtime32` 및 `time_t` 으로 정의할 수 `__time32_t`합니다. 그렇지 않으면이 64 비트 플랫폼에서 허용 되지 않으므로 2038 년 1 월 18 일 후 응용 프로그램이 실패할 수 있습니다 어떤 경우 든 때문에 두는 것이 좋습니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 `timer` 가 null 포인터 또는 타이머 값이 음수 이면 이러한 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 함수가 반환 `NULL` 설정 `errno` 를 `EINVAL`합니다.  
  
## 설명  
 `_gmtime32` 함수 세분화는 `timer` 값 형식의 정적으로 할당 된 구조에 저장 합니다 `tm`, 시간에 정의 된 합니다. 8. 값 `timer` 에 대 한 호출에서 가져온 일반적으로 `time` 함수입니다.  
  
> [!NOTE]
>  대부분의 경우에서 대상 환경 일광 절약 시간이 적용 되는지 확인 하려고 시도 합니다. C 런타임 라이브러리에서는 일광 절약 시간 \(DST\)의 계산 구현을 위한 미국의 규칙이 사용 됩니다 가정 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`gmtime`|\<time.h\>|  
|`_gmtime32`|\<time.h\>|  
|`_gmtime64`|\<time.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 예제  
  
```  
  
      // crt_gmtime.c  
// compile with: /W3  
// This program uses _gmtime64 to convert a long-  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm *newtime;  
   __int64 ltime;  
   char buff[80];  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:  
   newtime = _gmtime64( &ltime ); // C4996  
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s  
   asctime_s( buff, sizeof(buff), newtime );  
   printf( "Coordinated universal time is %s\n", buff );  
}  
```  
  
```Output  
Coordinated universal time은 2 월 12 일 화요일 11:31 23 2002  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)