---
title: "strcoll 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strcoll"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "코드 페이지, 문자열 비교에 사용"
  - "strcoll 함수"
  - "문자열 비교[C++], 문화권별"
  - "문자열[C++], 코드 페이지로 비교"
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strcoll 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 `strcoll` 와 `wcscoll` 함수는 현재 사용하는 로캘 코드 페이지의 `LC_COLLATE` 범주 설정에 따라 두 문자열을 비교합니다.  각각의 `_mbscoll` 함수는 현재 사용중인 멀티 바이트 코드 페이지에 따라 두 문자열을 비교합니다.  비교에 대한 인터넷의 차이점과 현제 코드 페이지에서 사전순 문자 순서와 문자집합 순서사에서 다른점이 있을때, 문자열 비교에 대한 `coll`을 사용합니다.  문자열 동일성에 대해 테스트에 대해 해당 `cmp` 함수들을 사용합니다.  
  
### strcoll 함수  
  
|SBCS|유니코드\(Unicode\)|MBCS|설명|  
|----------|---------------------|----------|--------|  
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[\_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|두 문자열들을 분석합니다.|  
|[\_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[\_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[\_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|두 개의 문자열 \(대\/소문자 구분 없이\)을 분석합니다.|  
|[\_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|두 문자열의 첫 `count` 문자를 분석합니다.|  
|[\_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|\(인식하지 않는 경우\) 두 문자열의 첫 `count` 문자들을 분석합니다.|  
  
## 설명  
 이러한 함수들\(`strcoll`, `stricoll`, `_strncoll` 과 `_strnicoll`\)의 싱글바이트 문자\(SBCS\) 버전은 `string1` 과 `string2` 을 현재 범주의 `LC_COLLATE` 범주 설정에따라 비교합니다.  이러한 함수는 대조 시퀀스를 제공하는 로캘 코드 페이지를 사용하는 `strcoll` 함수들에서 해당 `strcmp` 함수들과는 다릅니다.  문자열 집합 순서와 사전 순서상 문자 순서가 다른 로캘들에서 문자열 비교는, `strcmp` 함수들보다는 `strcoll` 함수들을 사용해야합니다.  `LC_COLLATE` 에 대한 자세한 내용은 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 를 참조하십시오.  
  
 일부 코드 페이지와 해당 문자 집합에 대한 문자 집합에, 문자의 순서 lexicographic 문자 순서와에서 다를 수 있습니다.  "C" 로케일에서 이 경우가 아니라면: ASCII 문자 집합의 문자 순서는 문자 lexicographic 순서와 동일합니다.  그러나 특정 유럽 코드 페이지에서 예를 들어, 문자 'a' \(값 0x61\) 앞 문자 'ä' \(0xE4\)의 값은 문자 집합, 그러나 사전 순으로 문자를 제외한 문자 'ä' 앞에 'a' 입니다.  이러한 상황에서 사전순서상의 비교를 수행하려면 `strcmp` 대신 `strcoll` 를 사용하세요.  결과 문자열에 `strcmp`을 사용하는 것 대신에, 원본 문자열에 `strxfrm`를 사용할 수 있습니다.  
  
 `strcoll`, `stricoll`, `_strncoll` 과 `_strnicoll` 는 자동적으로 사용하는 현재 로캘 코드페이지에 따라 와이드 문자\(유니코드\) 대응으로써, 멀티바이트 문자열을 처리합니다.  그러나, 이러한 함수의 멀티 바이트 문자\(MBCS\) 버전은 현재 사용 중인 멀티 바이트 코드 페이지에 따라 문자 단위로 합쳐집니다.  
  
 이 `coll` 함수는 사전순으로 비교한 문자열을 비교하기 때문에, `cmp` 함수는 같은 문자열을 쉽게 테스트하는 것 인데도 `coll` 함수는 같은 `cmp` 버전보다 더 많이 느립니다.  그럼에도, 문자 사이는 차이점이 현재 코드 페이지에 순서와 lexicographic 문자 순서 설정 및 문자열 비교에 대한 관심의 차이가 있는 경우에 `coll` 함수를 사용해야 합니다.  
  
## 참고 항목  
 [로캘](../c-runtime-library/locale.md)   
 [문자열 조작](../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)