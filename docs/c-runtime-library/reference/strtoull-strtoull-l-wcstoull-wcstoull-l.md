---
title: "strtoull, _strtoull_l, wcstoull, _wcstoull_l | Microsoft Docs"
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
  - "_strtoull_l"
  - "_wcstoull_l"
  - "strtoull"
  - "wcstoull"
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
  - "_wcstoull_l"
  - "_tcstoull"
  - "_tcstoull_l"
  - "wcstoull"
  - "_strtoull_l"
  - "strtoull"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoull_l 함수"
  - "_tcstoull 함수"
  - "_tcstoull_l 함수"
  - "_wcstoull_l 함수"
  - "strtoull 함수"
  - "wcstoull 함수"
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strtoull, _strtoull_l, wcstoull, _wcstoull_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 부호 없는 정수 값\(Long\)으로 변환합니다.  
  
## 구문  
  
```  
unsigned long long strtoull(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long long _strtoull_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long long wcstoull(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long long _wcstoull_l(  
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
 검색을 중지하는 문자에 대한 포인터입니다.  
  
 `base`  
 사용할 번호 기준입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `strtoull`는 있을 경우 반환된 값 또는 오버플로일 때는 `ULLONG_MAX`를 반환합니다.  `strtoull`은 변환을 수행할 수 없는 경우 0을 반환합니다.  `wcstoull`이 analogously 값을 `strtoull`에 반환 합니다.  두 함수 모두 오버플로 또는 언더플로가 발생하면 `errno`가 `ERANGE`로 설정됩니다.  
  
 반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오.  
  
## 설명  
 이러한 각 함수는 입력 문자열 `nptr`을 `unsigned long long` 정수 값으로 변환합니다.  
  
 `strtoull`는 숫자 부분으로 인식할 수 없는 첫 번째 문자에서 문자열 `nptr` 읽기를 중단합니다.  이는 null 종결 문자일 수 있거나 `base` 보다 크거나 동일한 첫 번째 숫자일 수 있습니다.  로캘의 `LC_NUMERIC` 범주는 `nptr`에서 기수 문자 인식 여부를 결정합니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `strtoull` 및 `wcstoull`는 현재 로켈을 사용합니다. `_strtoull_l` 및 `_wcstoull_l`은 대신 전달되지만 동일하지는 않은 로켈을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `endptr`이 `NULL`이 아닌 경우 검색을 중지시키는 문자에 대한 포인터는 `endptr`가 가리키는 위치에 저장됩니다.  변환을 수행할 수 없는 경우\(유효 숫자를 찾을 수 없거나 잘못된 기준이 지정됨\) `nptr`의 값은 `endptr`가 가리키는 위치에 저장됩니다.  
  
 `wcstoull`는 `strtoull`의 와이드 문자 버전이며, `nptr` 인수는 와이드 문자 문자열입니다.  그렇지 않으면 이러한 함수는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcstoull`|`strtoull`|`strtoull`|`wcstoull`|  
|`_tcstoull_l`|`strtoull_l`|`_strtoull_l`|`_wcstoull_l`|  
  
 `strtoull`에서는 다음 양식의 문자열을 가리키는 `nptr`를 예상합니다.  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; \[`letters`\]\]  
  
 `whitespace`는 무시되는 공백 및 탭 문자를 포함할 수 있으며 `digits`는 하나 이상의 10진수입니다. `letters`는 문자 'a' ~ 'z'\(또는 'A' ~ 'Z'\)입니다.  이 폼에 맞지 않는 첫 번째 문자는 검색을 중지합니다.  `base`가 2와 36 사이에 있으면 번호의 기준으로 사용됩니다.  `base`가 0이 되는 경우 `nptr`에 의해 지시되는 문자열의 최초 문자가 베이스 결정에 사용됩니다.  첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'인 경우 문자열은 8진수 정수로 해석됩니다.  첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'인 경우 문자열은 16진수 정수로 해석됩니다.  첫 번째 문자가 '1'부터 '9'이면 문자열은 10진수로 해석됩니다.  문자 'a'부터 'z'\(또는 'A'부터 'Z'\)는 10\-35 값이 할당됩니다. 즉, 할당된 값이 `base` 보다 작은 문자만이 허용됩니다.  기준 범위를 벗어나는 첫 번째 문자는 검색을 중지합니다.  예를 들어 `base`가 0이 되어 검색된 첫 번째 문자가 '0'이 되는 경우 8진수 정수를 정하여 '8' 이나 '9'의 문자로 검색은 중지됩니다.  `strtoull`는 더하기 기호 \(`+`\) 또는 빼기 기호 \(`–`\)를 붙여야합니다. 앞에 빼기 기호는 부정된 반환 값을 나타냅니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strtoull`|\<stdlib.h\>|  
|`wcstoull`|\<stdlib.h\> 또는 \<wchar.h\>|  
|`_strtoull_l`|\<stdlib.h\>|  
|`_wcstoull_l`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
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
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoll, \_strtoll\_l, wcstoll, \_wcstoll\_l](../../c-runtime-library/reference/strtoll-strtoll-l-wcstoll-wcstoll-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)