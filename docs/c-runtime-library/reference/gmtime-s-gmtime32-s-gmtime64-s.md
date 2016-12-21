---
title: "gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft Docs"
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
  - "_gmtime32_s"
  - "gmtime_s"
  - "_gmtime64_s"
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
  - "_gmtime_s"
  - "gmtime64_s"
  - "gmtime32_s"
  - "_gmtime64_s"
  - "gmtime_s"
  - "_gmtime32_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "gmtime_s 함수"
  - "gmtime32_s 함수"
  - "시간 함수"
  - "gmtime64_s 함수"
  - "_gmtime64_s 함수"
  - "시간 구조체 변환"
  - "_gmtime_s 함수"
  - "_gmtime32_s 함수"
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gmtime_s, _gmtime32_s, _gmtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구조에는 시간 값을 변환합니다. 이 버전의 [\_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 에 설명 된 대로 보안이 강화 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### 매개 변수  
 `_tm`  
 에 대 한 포인터는 `tm` 구조입니다. 계산 된 값을 유지 하는 반환 된 구조체의 필드는 `timer` utc에서 대신 현지 시간으로 인수입니다.  
  
 `time`  
 저장 된 시간에 대 한 포인터입니다. 자정 이후 경과 된 초 시간 표현 됩니다 \(00: 00:00\), 1970 년 1 월 1 일 협정 세계시 \(UTC\)입니다.  
  
## 반환 값  
 성공 하면 0입니다. 반환 값은 오류가 발생 하는 경우 오류 코드는 합니다. 오류 코드는 다음과 같은; Errno.h에서 정의 됩니다. 이러한 오류의 목록을 보려면 [errno](../../c-runtime-library/errno-constants.md)합니다.  
  
### 오류 조건  
  
|`_tm`|`time`|반환|값 `_tm`|  
|-----------|------------|--------|-------------|  
|`NULL`|any|`EINVAL`|수정 되지 않습니다.|  
|하지 `NULL` \(올바른 메모리 포인트\)|`NULL`|`EINVAL`|모든 필드를\-1로 설정 합니다.|  
|Not `NULL`|\< 0|`EINVAL`|모든 필드를\-1로 설정 합니다.|  
  
 첫 번째 두 오류 상태를의 경우는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## 설명  
 `_gmtime32_s` 함수 세분화는 `time` 값 형식의 구조에 저장 합니다 `tm`, Time.h에서 정의 합니다. 구조체의 주소가 전달 됩니다 `_tm`합니다. 값 `time` 에 대 한 호출에서 가져온 일반적으로 `time` 함수입니다.  
  
> [!NOTE]
>  대상 환경 일광 절약 시간이 적용 되는지 확인 하십시오. C 런타임 라이브러리에서는 일광 절약 시간 계산 구현을 위한 미국의 규칙이 가정 합니다.  
  
 각 구조 필드의 형식입니다 `int`, 는 다음 표에 표시 된 것 처럼입니다.  
  
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
  
 `_gmtime64_s`, 를 사용 하는 `__time64_t` 구조, 23시 59분: 59 까지의 3000 년 12 월 31 일 UTC 표시 해야 하는 날짜 허용 하는 반면 `gmtime32_s` 만 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다. 자정 1970 년 1 월 1 일에 이러한 두 함수에 대 한 날짜 범위의 하한값입니다.  
  
 `gmtime_s` 계산 되는 인라인 함수 인지 `_gmtime64_s` 및 `time_t` 같습니다 `__time64_t`합니다. 컴파일러에서 `time_t`를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 이렇게 하면이로 인해 `gmtime_s` 인라인 되도록 `_gmtime32_s`합니다. 응용 프로그램 2038 년 1 월 18 일 후 실패 하 고 64 비트 플랫폼에서 허용 되지 않으므로 때문에이 권장 되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`gmtime_s`|\<time.h\>|  
|`_gmtime32_s`|\<time.h\>|  
|`_gmtime64_s`|\<time.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 예제  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
Coordinated universal time은 4 월 25 일 금요일 20시 12분: 33 2003  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)