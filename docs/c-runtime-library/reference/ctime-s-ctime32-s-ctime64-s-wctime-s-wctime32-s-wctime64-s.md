---
title: "ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64_s"
  - "_wctime32_s"
  - "ctime_s"
  - "_wctime64_s"
  - "_ctime32_s"
  - "_wctime_s"
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
  - "ctime64_s"
  - "_ctime32_s"
  - "_tctime32_s"
  - "_ctime64_s"
  - "_wctime_s"
  - "_tctime_s"
  - "_tctime64_s"
  - "ctime_s"
  - "ctime32_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctime32_s 함수"
  - "ctime64_s 함수"
  - "_tctime64_s 함수"
  - "_wctime_s 함수"
  - "tctime_s 함수"
  - "_wctime64_s 함수"
  - "ctime_s 함수"
  - "ctime32_s 함수"
  - "_ctime64_s 함수"
  - "tctime64_s 함수"
  - "wctime64_s 함수"
  - "wctime_s 함수"
  - "_tctime_s 함수"
  - "tctime32_s 함수"
  - "wctime32_s 함수"
  - "시간, 변환"
  - "_ctime32_s 함수"
  - "_tctime32_s 함수"
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간 값을 문자열로 변환 하 고 현지 표준 시간대 설정에 대 한 조정 합니다. 이 버전의 [ctime, \_ctime64, \_wctime, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) 에 설명 된 대로 보안이 강화 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `buffer`  
 26 개 문자를 포함 하기에 충분 해야 합니다. 문자 문자열 결과에 대 한 포인터 또는 `NULL`경우:  
  
-   `time` 1970 년 1 월 1 일 자정 UTC 이전의 날짜를 나타냅니다.  
  
-   사용 하는 경우 `_ctime32_s` 또는 `_wctime32_s` 및 `time` 23시 59분: 59 2038 년 1 월 18 일 UTC 이후 날짜를 나타냅니다.  
  
-   사용 하는 경우 `_ctime64_s` 또는 `_wctime64_s` 및 `time` 23시 59분: 59 3000 년 12 월 31 일 UTC 이후 날짜를 나타냅니다.  
  
-   사용 하는 경우 `_ctime_s` 또는 `_wctime_s`, 이러한 함수는 이전 함수에 대 한 래퍼입니다. 설명 부분을 참조하세요.  
  
 \[in\] `numberOfElements`  
 버퍼의 크기입니다.  
  
 \[in\] t`ime`  
 저장 된 시간에 대 한 포인터입니다.  
  
## 반환 값  
 성공 하면 0입니다. 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 잘못 된 매개 변수가 인 한 오류 이면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 되는 경우에 오류 코드가 반환 됩니다. 오류 코드는 ERRNO에 정의 됩니다. H. 이러한 오류의 목록을 보려면 [errno](../../c-runtime-library/errno-constants.md)합니다. 각 오류 조건에 대해 발생 하는 실제 오류 코드는 다음 표에 표시 됩니다.  
  
## 오류 조건  
  
|`buffer`|`numberOfElements`|`time`|반환|값 `buffer`|  
|--------------|------------------------|------------|--------|----------------|  
|`NULL`|any|any|`EINVAL`|수정 안 됨|  
|하지 `NULL` \(올바른 메모리 포인트\)|0|any|`EINVAL`|수정 안 됨|  
|Not `NULL`|0 \< \< 26 크기 조정|any|`EINVAL`|빈 문자열|  
|Not `NULL`|\>\= 26|NULL|`EINVAL`|빈 문자열|  
|Not `NULL`|\>\= 26|\< 0|`EINVAL`|빈 문자열|  
  
## 설명  
 `ctime_s` 함수 변환으로 저장 하는 시간 값을 [time\_t](../../c-runtime-library/standard-types.md) 문자열로 구조입니다.`time` 값에 대 한 호출에서 가져온 일반적으로 [시간](../../c-runtime-library/reference/time-time32-time64.md), 를 자정 이후 경과 된 초 수를 반환 \(00: 00:00\), 1970 년 1 월 1 일 협정 세계시 \(UTC\)입니다. 반환 값 문자열 정확 하 게 26 개 문자를 포함 하며는 형식을 갖습니다.  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24 시간제 사용 됩니다. 모든 필드는 상수는 너비가 있습니다. 줄 바꿈 문자 \('\\n'\) 및 null 문자 \('\\0'\)는 문자열의 마지막 두 자리를 차지 합니다.  
  
 변환 된 문자열은 현지 표준 시간대 설정에 따라 조정할 수 있습니다. 참조는 `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), 및 [localtime32\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) 의 현지 시간을 구성 하는 방법에 대 한 정보에 대 한 함수 및 [\_tzset](../../c-runtime-library/reference/tzset.md) 시간대 환경 및 전역 변수를 정의 하는 방법에 대 한 정보에 대 한 함수입니다.  
  
 `_wctime32_s` 및 `_wctime64_s` 의 와이드 문자 버전은 `_ctime32_s` 및 `_ctime64_s`; 와이드 문자 문자열에 대 한 포인터를 반환 합니다. 그렇지 않으면 `_ctime64_s`, `_wctime32_s`, 및 `_wctime64_s` 동일 하 게 작동 `_ctime32_s`합니다.  
  
 `ctime_s` 계산 되는 인라인 함수 이며 `_ctime64_s` 및 `time_t` 같습니다 `__time64_t`합니다. 컴파일러에서 `time_t`를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 이렇게 하면이로 인해 `ctime_s` 로 계산 `_ctime32_s`합니다. 응용 프로그램 2038 년 1 월 18 일 후 실패 하 고 64 비트 플랫폼에서 허용 되지 않으므로 때문에이 권장 되지 않습니다.  
  
 C \+ \+에서 이러한 함수를 사용 하 여 단순화 되어 템플릿 오버 로드 합니다. 오버 로드는 버퍼 길이 자동으로 유추할 수, 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`ctime_s,`<br /><br /> `_ctime32_s,`<br /><br /> `_ctime64_s`|\<time.h\>|  
|`_wctime_s,`<br /><br /> `_wctime32_s,`<br /><br /> `_wctime64_s`|\<. h \> 또는 \< wchar.h \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## 샘플 출력  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)