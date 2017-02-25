---
title: "ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64"
  - "_wctime32"
  - "ctime"
  - "_wctime64"
  - "_ctime32"
  - "_wctime"
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
  - "_wctime64"
  - "_ctime32"
  - "_tctime"
  - "_wctime"
  - "_wctime32"
  - "_tctime64"
  - "_ctime64"
  - "ctime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tctime64 함수"
  - "_ctime32 함수"
  - "ctime32 함수"
  - "_wctime 함수"
  - "wctime64 함수"
  - "_tctime64 함수"
  - "_tctime32 함수"
  - "_ctime64 함수"
  - "_wctime64 함수"
  - "ctime 함수"
  - "wctime32 함수"
  - "ctime64 함수"
  - "_wctime32 함수"
  - "_tctime 함수"
  - "tctime32 함수"
  - "tctime 함수"
  - "wctime 함수"
  - "시간, 변환"
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간 값을 문자열로 변환 하 고 현지 표준 시간대 설정에 대 한 조정 합니다. 이러한 함수의 더 안전한 버전은 사용할 수 있습니다. 참조 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)합니다.  
  
## 구문  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### 매개 변수  
 `timer`  
 저장 된 시간에 대 한 포인터입니다.  
  
## 반환 값  
 문자 문자열 결과에 대 한 포인터입니다.`NULL` 경우에 반환 됩니다.  
  
-   `time` 1970 년 1 월 1 일 자정 UTC 이전의 날짜를 나타냅니다.  
  
-   사용 하는 경우 `_ctime32` 또는 `_wctime32` 및 `time` 23시 59분: 59 2038 년 1 월 18 일 UTC 이후 날짜를 나타냅니다.  
  
-   사용 하는 경우 `_ctime64` 또는 `_wctime64` 및 `time` 23시 59분: 59 3000 년 12 월 31 일 UTC 이후 날짜를 나타냅니다.  
  
 `ctime` 계산 되는 인라인 함수 인지 `_ctime64` 및 `time_t` 같습니다 `__time64_t`합니다. 컴파일러가를 해석 하는 경우 `time_t` 이전 32 비트로 `time_t`, 를 정의할 수 있습니다 `_USE_32BIT_TIME_T`합니다. 이렇게 하면이로 인해 `ctime` 로 계산 `_ctime32`합니다. 응용 프로그램 2038 년 1 월 18 일 후 실패 하 고 64 비트 플랫폼에서 허용 되지 않으므로 때문에이 권장 되지 않습니다.  
  
## 설명  
 `ctime` 함수 변환으로 저장 하는 시간 값을 [time\_t](../../c-runtime-library/standard-types.md) 에 문자열 값입니다.`timer` 값에 대 한 호출에서 가져온 일반적으로 [시간](../../c-runtime-library/reference/time-time32-time64.md), 자정 이후 경과 된 초 수를 반환 \(00: 00:00\), 1970 년 1 월 1 일 협정 세계시 \(UTC\)입니다. 반환 값 문자열 정확 하 게 26 개 문자를 포함 하며는 형식을 갖습니다.  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24 시간제 사용 됩니다. 모든 필드는 상수는 너비가 있습니다. 줄 바꿈 문자 \('\\n'\) 및 null 문자 \('\\0'\)는 문자열의 마지막 두 자리를 차지 합니다.  
  
 변환 된 문자열은 현지 표준 시간대 설정에 따라 조정할 수 있습니다. 참조는 `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), 및 [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 현지 시간 구성에 대 한 함수 및 [\_tzset](../../c-runtime-library/reference/tzset.md) 시간대 환경 및 전역 변수를 정의 하는 방법에 대 한 세부 정보에 대 한 함수입니다.  
  
 에 대 한 호출 `ctime` 수정 하 여 사용 되는 단일 정적으로 할당 된 버퍼는 `gmtime` 및 `localtime` 함수입니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과 삭제합니다.`ctime` 정적 버퍼를 공유 하는 `asctime` 함수입니다. 에 대 한 호출 이므로 `ctime` 모든 이전 호출의 결과 소멸 `asctime`, `localtime`, 또는 `gmtime`합니다.  
  
 `_wctime` 및 `_wctime64` 의 와이드 문자 버전은 `ctime` 및 `_ctime64`; 와이드 문자 문자열에 대 한 포인터를 반환 합니다. 그렇지 않으면 `_ctime64`, `_wctime`, 및 `_wctime64` 동일 하 게 작동 `ctime`합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 `timer` 가 null 포인터 또는 타이머 값이 음수 이면 이러한 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 함수가 반환 `NULL` 설정 `errno` 를 `EINVAL`합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`ctime`|\<time.h\>|  
|`_ctime32`|\<time.h\>|  
|`_ctime64`|\<time.h\>|  
|`_wctime`|\<. h \> 또는 \< wchar.h \>|  
|`_wctime32`|\<. h \> 또는 \< wchar.h \>|  
|`_wctime64`|\<. h \> 또는 \< wchar.h \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
시간은 2 월 13 일 수요일 16시 04분: 43 2002  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)