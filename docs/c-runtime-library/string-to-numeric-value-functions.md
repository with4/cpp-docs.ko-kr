---
title: "문자열을 숫자 값으로 변환하는 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstoui64"
  - "_tcstoi64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "구문 분석, 숫자 문자열"
  - "문자열 변환, 숫자 값으로"
ms.assetid: 11cbd9ce-033b-4914-bf66-029070e7e385
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 문자열을 숫자 값으로 변환하는 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

-   [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)  
  
-   [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)  
  
-   [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)  
  
-   [\_strtoi64, \_wcstoi64, \_strtoi64\_l, \_wcstoi64\_l](../c-runtime-library/reference/strtoi64-wcstoi64-strtoi64-l-wcstoi64-l.md)  
  
-   [\_strtoui64, \_wcstoui64, \_strtoui64\_l, \_wcstoui64\_l](../c-runtime-library/reference/strtoui64-wcstoui64-strtoui64-l-wcstoui64-l.md)  
  
## 설명  
 **strtod**  함수 군의 각 함수는 숫자에 null로 끝나는 문자열로 변환합니다.  다음 표에서는 사용할 수 있는 함수를 보여 줍니다.  
  
|Function|설명|  
|--------------|--------|  
|`strtod`|문자열을 배정밀도 부동 소수점 값으로 변환합니다.|  
|`strtol`|문자열을 정수 \(long\)로 변환합니다.|  
|`strtoul`|문자열을 부호 없는 정수 \(long\)로 변환합니다.|  
|`_strtoi64`|문자열을 64비트 `__int64` 정수로 변환합니다.|  
|`_strtoui64`|문자열을 부호 없는 64 비트 `__int64` 정수로 변환합니다.|  
  
 `wcstod`, `wcstol`, `wcstoul`, 및 `_wcstoi64` 은 각각 `strtod`, `strtol`, `strtoul`, 및 `_strtoi64` 의 와이드 문자 버전입니다.  각 와이드 문자 함수에 문자열 인수는 와이드 문자열입니다. 그렇지 않으면 각 함수는 단일 바이트 문자열에 대응하여 동일하게 작동합니다.  
  
 `strtod` 함수는 두 개의 인수를 사용 합니다: 첫 번째는 입력된 문자열이고, 두 번째는 변환 프로세스를 종료하는 문자에 대한 포인터 입니다.  `strtol`, `strtoul`, **\_strtoi64** 및 **\_strtoui64**  는 세 번째 인자로 변환 프로세스에서 사용 되는 기본 숫자를 받습니다.  
  
 입력 문자열은 지정한 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다.  각 함수는 숫자 부분으로 인식할 수 없는 첫 번째 문자에서 문자열 읽기를 중단합니다.  이는 null 종결 문자일 수 있습니다.  `strtol`, `strtoul`, `_strtoi64`, 및 `_strtoui64` 에 대해, 종료 문자는 또한 사용자가 제공한 숫자 기본 이상의 첫 번째 문자 수입니다.  
  
 중지 문자에 대한 포인터에 **NULL**  로 설정되지 않은 경우 끝 변환 문자로 사용자가 제공 한 포인터는 통화 시간, 스캔 대신이 저장됩니다.  변환 \(유효한 숫자가 찾을 수 없거나 잘못된베이스가 지정되었습니다\)을 실행할 수없는 경우 문자열 포인터의 값은 주소에 저장됩니다.  
  
 `strtod` 은 다음 형식의 문자열을 예상합니다:  
  
 \[*whitespace*\] \[*sign*\] \[`digits`\] \[**.**`digits`\] \[ {**d** &#124; **D** &#124; **e** &#124; **E**}\[*sign*\]`digits`\]  
  
 *whitespace* 은 무시되는 공백 또는 탭 문자이고, *sign* 부분은 플러스 \(**\+**\) 또는 마이너스 \(**–**\)에서 `digits`는 하나 이상의 10 진수입니다.  기수 문자 앞에 자릿수가 나타나지 않는 경우 하나 이상의 자릿수가 기수 문자 뒤에 나타나야 합니다.  10 진수는 소개서를 구성하는 지수\(**d**, **D**, **e**, or **E**\) 와 선택적으로 서명된 정수 다음에 올 수 있습니다.  지수부 또는 기수 문자가 나타나지 않는 경우 기수 문자는 문자열의 마지막 숫자를 따릅니다.  이 폼에 맞지 않는 첫 번째 문자는 검색을 중지합니다.  
  
 `strtol`, `strtoul`, `_strtoi64`, 및 `_strtoui64` 함수는 다음과 같은 형식의 문자열로 예상됩니다.  
  
 \[*whitespace*\] \[{**\+** &#124; **–**}\] \[**0** \[{ **x** &#124; **X** }\]\] \[`digits`\]  
  
 기본 인수가 2와 36 사이에 있으면 번호의 기준으로 사용됩니다.  것이 0 인 경우, 변환 종료 포인터에 의해 참조되는 첫 번째 문자는 기본을 결정하는 데 사용된다.  첫 문자가 0이고, 두 번째 문자가 'X'또는 'X'가 아닌 경우, 문자열 8진수 정수로 해석되고, 그렇지 않은 경우는 10진수로 해석됩니다.  첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'인 경우 문자열은 16진수 정수로 해석됩니다.  첫 번째 문자가 '1'부터 '9'이면 문자열은 10진수로 해석됩니다.  문자 'a'부터 'z'\(또는 'A'부터 'Z'\)는 10\-35 값이 할당됩니다. 즉, 할당된 값이 *base* 보다 작은 문자만이 허용됩니다.  `strtoul` 및 `_strtoui64` 는 더하기 \(**\+**\) 또는 빼기 \(**–**\) 접두사를 붙여야 합니다. 맨 앞의 빼기 접두사는 반환 값이 부인됩니다.  
  
 출력 값은 로캘의 `LC_NUMERIC` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  이 **\_l** 접미사가 없는 이러한 함수의 버전은 해당 로캘 종속 동작에 현재 로캘을 사용합니다. **\_l** 접미사가 있는 버전은 대신 전달 된 로캘 매개 변수를 사용하는 경우을 제외하고는 동일합니다.  
  
 이 함수에 의해 반환되는 값이 오버 플로 또는 언더 플로를 야기하는 경우, 또는 변환 할 수없는 경우, 특별한 경우 값은 아래와 같이 반환됩니다.  
  
|Function|조건|반환 값|  
|--------------|--------|----------|  
|`strtod`|오버플로가 발생했습니다.|\+\/\- `HUGE_VAL`|  
|`strtod`|언더플로 또는 변환 없음|0|  
|`strtol`|\+ Overflow|**LONG\_MAX**|  
|`strtol`|\- Overflow|**LONG\_MIN**|  
|`strtol`|언더플로 또는 변환 없음|0|  
|`_strtoi64`|\+ Overflow|**\_I64\_MAX**|  
|`_strtoi64`|\- Overflow|**\_I64\_MIN**|  
|`_strtoi64`|변환이 수행되지 않습니다.|0|  
|`_strtoui64`|오버플로가 발생했습니다.|**\_UI64\_MAX**|  
|`_strtoui64`|변환이 수행되지 않습니다.|0|  
  
 **\_I64\_MAX**, \_**I64\_MIN**, 및  **\_UI64\_MAX** 는 LIMITS.H 에 정의됩니다.  
  
 `wcstod`, `wcstol`, `wcstoul`, `_wcstoi64`, 및 `_wcstoui64` 은 각 와이드 문자 함수에 대한 변환의 최종 인수에 대한 포인트인 `strtod`, `strtol`, `strtoul`, `_strtoi64`, 및 `_strtoui64` 의 와이드 문자 버전입니다.  그렇지 않으면, 이러한 와이드 문자 기능은 각각의 단일 바이트 문자의 대응에 동일하게 동작합니다.  
  
## 참고 항목  
 [데이터 변환](../c-runtime-library/data-conversion.md)   
 [로캘](../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [부동 소수점 지원](../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)