---
title: "strtoul, _strtoul_l, wcstoul, _wcstoul_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcstoul_l"
  - "_strtoul_l"
  - "strtoul"
  - "wcstoul"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strtoul"
  - "_tcstoul"
  - "wcstoul"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoul_l 함수"
  - "_tcstoul 함수"
  - "_wcstoul_l 함수"
  - "문자열 변환, 정수로"
  - "strtoul 함수"
  - "strtoul_l 함수"
  - "tcstoul 함수"
  - "wcstoul 함수"
  - "wcstoul_l 함수"
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strtoul, _strtoul_l, wcstoul, _wcstoul_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 부호 없는 정수 값\(Long\)으로 변환합니다.  
  
## 구문  
  
```  
unsigned long strtoul(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long _strtoul_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long wcstoul(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long _wcstoul_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `nptr`  
 변환할 Null 종료 문자열입니다.  
  
 `endptr`  
 스캔을 중지하는 문자에 대한 포인터입니다.  
  
 `base`  
 사용할 번호 기준입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `strtoul`는 있을 경우 반환된 값 또는 오버플로일 때는 `ULONG_MAX`를 반환합니다.  `strtoul` 은 변환을 수행할 수 없는 경우 0을 반환합니다.  `wcstoul`이 analogously 값을 `strtoul`에 반환 합니다.  두 함수 모두 오버플로 또는 언더플로가 발생하면 `errno`가 `ERANGE`로 설정됩니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 을 참조하십시오.  
  
## 설명  
 이러한 각 함수는 입력 문자열 `nptr` 을 `unsigned` `long` 정수 값으로 변환합니다.  
  
 `strtoul`는 숫자 부분으로 인식할 수 없는 첫 번째 문자에서 문자열 `nptr` 읽기를 중단합니다.  이는 null 종결 문자 이거나 `base` 와 같거나 더 큰 첫번째 숫자 일 수 있습니다.  현재 로캘의 `LC_NUMERIC` 범주 설정은 `nptr`에서 기수 문자 인식 여부를 결정합니다. 자세한 내용은 [](../../c-runtime-library/reference/setlocale-wsetlocale.md "setlocale, _wsetlocale")을 참조하십시오.  `strtoul` 및 `wcstoul` 는 현재 로켈을 사용합니다. `_strtoul_l` 및 `_wcstoul_l` 는 통과된 로켈을 대신 사용하는 것을 제외하고는 일치합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `endptr` 가 `NULL`이 아닌 경우 스캔을 중지시키는 문자에 대한 포인터는 `endptr`가 가리키는 위치에 저장됩니다.  변환을 수행할 수 없는 경우\(유효 숫자를 찾을 수 없거나 잘못된 기준이 지정됨\), `nptr` 의 값은 `endptr`가 가리키는 위치에 저장됩니다.  
  
 `wcstoul`는 `strtoul`의 와이드 문자 버전이며, `nptr` 인수는 와이드 문자 문자열입니다.  그렇지 않으면 이러한 함수는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcstoul`|`strtoul`|`strtoul`|`wcstoul`|  
|`_tcstoul_l`|`strtoul_l`|`_strtoul_l`|`_wcstoul_l`|  
  
 `strtoul`에서는 다음 양식의 문자열을 가리키는 `nptr`를 예상합니다.  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits`\]  
  
 하나의 `whitespace` 는 공백과 탭 문자로 구성될 수 있으며 무시 됩니다; `digits` 는 하나 이상의 10진수 숫자입니다.  이 폼에 맞지 않는 첫 번째 문자는 검색을 중지합니다.  `base`가 2와 36 사이에 있으면 번호의 기준으로 사용됩니다.  `base`가 0이 되는 경우 `nptr`가 지시하는 문자열의 최초 문자가 베이스 결정에 사용됩니다.  첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'가 아닌 경우 문자열은 8진수 정수로 해석됩니다.  첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'인 경우 문자열은 16진수 정수로 해석됩니다.  첫 번째 문자가 '1'부터 '9'이면 문자열은 10진수로 해석됩니다.  문자 'a'부터 'z'\(또는 'A'부터 'Z'\)는 10\-35 값이 할당됩니다. 즉, 할당된 값이 `base` 보다 작은 문자만이 허용됩니다.  기준 범위를 벗어나는 첫 번째 문자는 검색을 중지합니다.  예를 들어 `base` 가 0이고 스캔된 첫 번째 문자가 '0'이 되는 경우 8진수 정수가 되고 '8' 또는 '9' 문자가 스캔을 중지 시킬 수 있습니다.  `strtoul` 는 더하기 기호 \(`+`\) 또는 빼기 기호 \(`–`\)를 붙여야합니다. 앞에 빼기 기호는 부정된 반환 값을 나타냅니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strtoul`|\<stdlib.h\>|  
|`wcstoul`|\<stdlib.h\> 또는 \<wchar.h\>|  
|`_strtoul_l`|\<stdlib.h\>|  
|`_wcstoul_l`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)