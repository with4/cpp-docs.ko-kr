---
title: "strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs"
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
  - "strftime"
  - "_wcsftime_l"
  - "_strftime_l"
  - "wcsftime"
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
  - "_tcsftime"
  - "strftime"
  - "wcsftime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strftime_l 함수"
  - "strftime 함수"
  - "tcsftime 함수"
  - "_wcsftime_l 함수"
  - "wcsftime 함수"
  - "_tcsftime 함수"
  - "시간 문자열"
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strftime, wcsftime, _strftime_l, _wcsftime_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간 문자열의 형식입니다.  
  
## 구문  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `strDest`  
 출력 문자열  
  
 `maxsize`  
 문자\(`char` 또는 `wchart_t`\)로 측정된 `strDest` 버퍼의 크기입니다.  
  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `timeptr`  
 `tm` 데이터 구조  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `strftime`은 `strDest`에 위치한 문자의 수를 반환하고 `wcsftime`는 상응하는 와이드 문자의 수를 반환합니다.  
  
 종료 null을 포함하여 문자의 최종 숫자가 `maxsize` 이상이면, `strftime` 및 `wcsftime` 모두 0을 반환하고 `strDest`의 내용은 지정되지 않습니다.  
  
 형식 지정 코드를 통해 `format`에 추가될 수 있는 모든 문자와 마찬가지로 `strDest`의 문자 수는 `format`의 리터럴 문자의 수와 같습니다.  문자열의 종료 null은 반환 값에서 세어지지 않습니다.  
  
## 설명  
 `strftime` 및 `wcsftime` 함수들은 `timeptr`의 `tm` 시간 값을 제공된 `format` 인수에 따라 형식을 지정하고 결과를 `strDest` 버퍼에 저장합니다*.* 최대 `maxsize` 문자가 문자열에 배치됩니다.  `timeptr` 구조체의 필드에 대한 자세한 설명은 [asctime](../../c-runtime-library/reference/asctime-wasctime.md)를 참조하십시오.  `wcsftime`는 `strftime`와 와이드 문자 같습니다. 문자열 포인터 인수는 와이드 문자열을 가리킵니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
> [!NOTE]
>  Visual C\+\+ 2005 이전 버전에서는 설명서에서 `wcsftime`의 `format` 매개 변수를 `const wchar_t *` 데이터 형식을 가진다고 설명하였으나, `format` 데이터 형식의 실제 구현은 `const char *`입니다.  `format`의 구현 데이터 형식은 이전 및 현재 설명서를 반영하기 위해 업데이트됩니다. `const wchar_t *` 입니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  `strDest`, `format` 또는 `timeptr`가 null 포인터이거나, `timeptr`에 의해 참조되는 `tm` 데이터 구조가 잘못되거나\(예를 들어, 시간 또는 날짜에 대한 범위 바깥의 값을 포함하는 경우\), 또는 `format` 문자열이 잘못된 서식 지정 코드를 포함하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 함수는 0을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 `format` 인수는 `printf`와 같이 하나 이상의 코드로 구성됩니다. 서식 지정 코드는 백분율 기호\(`%`\) 뒤에 위치합니다.  `%`로 시작하지 않는 문자는 `strDest`인 채 변경되지 않고 복사됩니다*.* 현재 로캘의 `LC_TIME` 범주는 `strftime`의 출력 형식 지정에 영향을 미칩니다. `LC_TIME` 에 대한 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 를 참조하십시오.\) `_l` 접미사가 없는 함수는 현재 설정된 로캘을 사용합니다.  `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `strftime`의 서식 지정 코드는 다음과 같습니다.  
  
 `%a`  
 약식된 요일 이름  
  
 `%A`  
 전체 요일 이름  
  
 `%b`  
 약식된 월 이름  
  
 `%B`  
 달의 전체 이름입니다.  
  
 `%c`  
 로캘에 적절한 날짜와 시간 표현  
  
 `%d`  
 10진수 형식의 한 달 내 일 \(01\-31\)  
  
 `%H`  
 24시간 형식의 시간 \(00\-23\)  
  
 `%I`  
 12시간 형식의 시간 \(01\-12\)  
  
 `%j`  
 10진수 형식의 연도 내 일 \(001\-366\)  
  
 `%m`  
 10진수 형식의 월 \(01\-12\)  
  
 `%M`  
 10진수 형식의 분 \(00\-59\)  
  
 `%p`  
 12시간 형식의 현재 로캘 A.M.\/P.M. 표시기  
  
 `%S`  
 10진수 형식의 초 \(00\-59\)  
  
 `%U`  
 일요일을 주의 첫째 날로 한 10진수 형식의 연도 내 주 \(00\-53\)  
  
 `%w`  
 10진수 형식의 요일 \(0 – 6. 일요일은 0\)  
  
 `%W`  
 월요일을 주의 첫째 날로 한 10진수 형식의 연도 내 주 \(00\-53\)  
  
 `%x`  
 현재 로캘에 대한 날짜 표현  
  
 `%X`  
 현재 로캘에 대한 시간 표현  
  
 `%y`  
 10진수 두 자리 형식의 연도 \(00\-99\)  
  
 `%Y`  
 10진수 형식의 연도 숫자  
  
 `%z, %Z`  
 레지스트리 설정에 따른 각각 표준 시간대 이름 또는 표준 시간대 약어입니다. 표준 시간대를 알 수 없는 경우 문자가 없습니다.  
  
 `%%`  
 백분율 기호  
  
 `printf` 함수에서와 같이, `#` 플래그는 모든 서식 지정 코드의 접두사일 수 있습니다.  이 경우, 다음과 같이 형식 코드의 의미가 변경됩니다.  
  
|코드 형식|의미|  
|-----------|--------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|`#`플래그는 무시됩니다.|  
|`%#c`|현재 로캘에 적절한 긴 날짜 및 시간 표현입니다.  예: "화요일, 3월 14, 1995, 12:41:29".|  
|`%#x`|현재 로캘에 적절한 긴 날짜 표현입니다.  예: "화요일, 3월 14, 1995".|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|\(있는 경우\) 앞에 오는 0을 제거합니다.|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strftime`|\<time.h\>|  
|`wcsftime`|\<time.h\> or \<wchar.h\>|  
|`_strftime_l`|\<time.h\>|  
|`_wcsftime_l`|\<time.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [time](../../c-runtime-library/reference/time-time32-time64.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## 참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [시간 관리](../../c-runtime-library/time-management.md)   
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)