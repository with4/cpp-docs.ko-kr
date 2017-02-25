---
title: "_strdate_s, _wstrdate_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdate_s"
  - "_wstrdate_s"
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
  - "_strdate_s"
  - "wstrdate_s"
  - "_wstrdate_s"
  - "strdate_s"
  - "_tstrdate_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "날짜, 복사"
  - "tstrdate_s 함수"
  - "wstrdate_s 함수"
  - "_tstrdate_s 함수"
  - "strdate_s 함수"
  - "날짜 복사"
  - "_strdate_s 함수"
  - "_wstrdate_s 함수"
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _strdate_s, _wstrdate_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

버퍼에 현재 시스템 날짜를 복사합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로, 보안 향상을 사용하여 [\_strdate, \_wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) 의 버전이 있습니다.  
  
## 구문  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `buffer`  
 서식이 지정된 날짜 문자열을 사용하여 채워진 버퍼에 대한 포인터입니다.  
  
 \[in\] `numberOfElements`  
 버퍼의 크기입니다.  
  
## 반환 값  
 성공시 0입니다.  오류가 발생한 경우 반환 값은 오류 코드입니다.  오류 코드는 ERRNO.H의에 정의되어있습니다; 이 기능에 의해 생성 된 정확한 오류에 대해 아래 표를 참조하세요.  오류 코드에 대한 자세한 정보는 [errno](../../c-runtime-library/errno-constants.md) 를 참조하세요.  
  
## 오류 조건  
  
|`buffer`|`numberOfElements`|반환|`buffer`의 내용입니다.|  
|--------------|------------------------|--------|----------------------|  
|`NULL`|모두|`EINVAL`|수정되지 않음|  
|`NULL` 이 아닙니다.\(유효한 버퍼에 대한 포인터\)|0|`EINVAL`|수정되지 않음|  
|`NULL` 이 아닙니다.\(유효한 버퍼에 대한 포인터\)|0 \< `numberOfElements` \< 9|`EINVAL`|빈 문자열|  
|`NULL` 이 아닙니다.\(유효한 버퍼에 대한 포인터\)|`numberOfElements` \>\= 9|0|설명에 지정 된 형식인 현재 날짜|  
  
## 보안 문제  
 만일 `numberOfElements` 매개 변수가 9보다 큰 경우, 버퍼에 대해 `NULL` 이 아닌 잘못된 값을 전달하는 것은 액세스 위반을 발생시킵니다.  
  
 `buffer` 의 실제 크기보다 큰 버퍼에 대한 값의 전달은 버퍼 오버런을 발생시킵니다.  
  
## 설명  
 이러한 함수는 `_strdate` 및 `_wstrdate` 의 보다 안전한 버전을 제공합니다.  `_strdate_s` 함수는 `buffer` 의해 지정된 버퍼에 대한 현재 시스템을 복사하거나, 서식이 지정된 `mm`\/`dd`\/`yy`, `mm` 이 달을 나타내는 두자리 숫자이고, `dd` 이 날을 나타내는 두개의 숫자이고, `yy` 이 연도의 마지막 두 숫자 입니다.  예를 들어, 문자열 `12/05/99` 는 1999 년 12 월 5 일을 나타냅니다.  버퍼에 적어도 9 자 보다 길어야 합니다.  
  
 `_wstrdate_s` 는 `_strdate_s` 의 와이드 문자 버전입니다. `_wstrdate_s` 인수와 반환 값은 와이드 문자 문자열입니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
 만일 `buffer` 이 `NULL` 포인터이거나 `numberOfElements` 이 9개의 문자들보다 적은 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로, 잘못된 매개변수 처리기가 호출됩니다.  만일 이러한 실행이 계속되는 경우, 이러한 함수들은 \-1을 반환하고 `errno` 을 `EINVAL` 로 설정합니다. 만약 버퍼가 `NULL` 이거나 `numberOfElements` 이 0과 같거나 더 적다면, 또는 `numberOfElements` 이 9보다 더 적다면, `errno` 이 `ERANGE` 으로 설정됩니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑:  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h\> or \<wchar.h\>|  
|`_strdate_s`|\<time.h\>|  
  
## 예제  
 [time](../../c-runtime-library/reference/time-time32-time64.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)