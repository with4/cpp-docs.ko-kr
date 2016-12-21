---
title: "_ismbc 루틴 | Microsoft Docs"
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
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbc 루틴"
  - "ismbc 루틴"
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbc 루틴
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이러한 **\_ismbc** 반복은 지정한 조건에 대해 `c` 인 멀티바이트 문자를 테스트합니다.  
  
|||  
|-|-|  
|[\_ismbcalnum, \_ismbcalnum\_l, \_ismbcalpha, \_ismbcalpha\_l, \_ismbcdigit, \_ismbcdigit\_l](../c-runtime-library/reference/ismbcalnum-functions.md)|[\_ismbcl0, \_ismbcl0\_l, \_ismbcl1, \_ismbcl1\_l, \_ismbcl2, \_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|  
|[\_ismbcgraph, \_ismbcgraph\_l, \_ismbcprint, \_ismbcprint\_l, \_ismbcpunct, \_ismbcpunct\_l, \_ismbcblank, \_ismbcblank\_l, \_ismbcspace, \_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|[\_ismbclegal, \_ismbclegal\_l, \_ismbcsymbol, \_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|  
|[\_ismbchira, \_ismbchira\_l, \_ismbckata, \_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|[\_ismbclower, \_ismbclower\_l, \_ismbcupper, \_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|  
  
## 설명  
 각 **\_ismbc** 반복의 테스트 결과는 적용한 멀티 바이트 코드 페이지를 따릅니다.  멀티 바이트 코드 페이지는 단일 바이트 영문자를 가집니다.  기본적으로 멀티 바이트 코드 페이지에 프로그램을 시작할 때 운영 체제에서 가져온 시스템 기본 ANSI 코드 페이지로 설정됩니다.  이 [\_getmbcp](../c-runtime-library/reference/getmbcp.md) 혹은 [\_setmbcp](../c-runtime-library/reference/setmbcp.md), 각각 사용한 멀티 바이트 코드 페이지 질의 혹은 변화할 수 있습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  이 **\_l** 접미사가 없는 이러한 함수의 버전은 해당 로캘 종속 동작에 현재 로캘을 사용합니다. **\_l** 접미사가 있는 버전은 대신 전달 된 로캘 매개 변수를 사용하는 경우을 제외하고는 동일합니다.  
  
|루틴|테스트 조건|932 코드 페이지 예제|  
|--------|------------|-------------------|  
|[\_ismbcalnum, \_ismbcalnum\_l](../c-runtime-library/reference/ismbcalnum-functions.md)|영, 숫자|0이 아닌 경우를 반환 하는 경우에만 `c` 는 영어 ASCII 문자의 싱글바이트 표시: 예제를 참조 하십시오 `_ismbcdigit` 및 `_ismbcalpha`.|  
|[\_ismbcalpha, \_ismbcalpha\_](../c-runtime-library/reference/ismbcalnum-functions.md)|Alphabetic|오직 `c` 이 ASCII 문자의 단일 바이트로 표현되는 경우에만 0이 아닌 것을 반환합니다 : `_ismbcupper` 과 `_ismbclower` 의 예제를 보세요; 혹은 가타카나 문자 : 0xA6\<\=`c`\<\=0xDF.|  
|[\_ismbcdigit, \_ismbcdigit\_l](../c-runtime-library/reference/ismbcalnum-functions.md)|\_DIGIT|0이 아닌 경우를 반환 하는 경우에만 `c` 는 ASCII 숫자는 1 바이트 표현: 0x30\<\=`c`\<0x39 \=.|  
|[\_ismbcgraph, \_ismbcgraph\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|그래픽|이 `c` 는 공백 \( \)을 제외한 모든 ASCII 또는 가타카나 인쇄 가능한 문자의 싱글 바이트 표현의 경우에만 반환 값이 0이 아닙니다.  자세한 내용은 `_ismbcdigit`, `_ismbcalpha` 및 `_ismbcpunct`를 참조하십시오.|  
|[\_ismbclegal, \_ismbclegal\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|유효한 멀티바이트 문자|첫째 바이트가 0이 아닌 경우 및 `c` 의 첫번째 바이트는 0x81\-0x9F 또는 0xE0 –의 범위 내에서 0xFC경우, 두 번째 바이트는 0x40 – 0x7E 또는 0x80\-의 범위 내에서 FC입니다.|  
|[\_ismbclower, \_ismbclower\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|소문자 알파벳|0이 아닌 경우를 반환 하는 경우에만 `c` 표현 싱글바이트 ASCII 소문자 영어 글자: 0x61\<\=`c`\<\= 0x7A.|  
|[\_ismbcprint, \_ismbcprint\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|인쇄 가능|모든 ASCII의 단일 표현 단일 바이트 혹은 공백 \( \) 을 포함한 인쇄 가능한 가타카나 문자는 `c` 경우에만 0이 아닌 것을 반환합니다 : `_ismbcspace`, `_ismbcdigit`, `_ismbcalpha` 과 `_ismbcpunct`를 보세요.|  
|[\_ismbcpunct, \_ismbcpunct\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|문장 부호|이 `c` 는 표현 싱글바이트 가타카나 또는 문장 부호 문자인 경우 반환 값이 0이 아닙니다.|  
|[\_ismbcblank, \_ismbcblank\_l,](../c-runtime-library/reference/ismbcgraph-functions.md)|스페이스나 수평 탭|이 `c` 이 가로 탭 문자 혹은 공백 문자의 1 바이트 표현의 경우에만 0이 아닌 것을 반환합니다 : `c`\=0x20 혹은 `c`\=0x09.|  
|[\_ismbcspace, \_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Whitespace|이 `c` 는 공백 문자인 경우 0이 아닌 값을 반환합니다 : `c`\=0x20 or 0x09\<\=`c`\<\=0x0D.|  
|[\_ismbcsymbol, \_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|멀티 바이트 기호|0이 아닌 경우를 반환 하는 경우에만 0x8141\<\=`c`\<\= 0x81AC를 반환합니다.|  
|[\_ismbcupper, \_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|대문자 알파벳|0이 아닌 경우를 반환 하는 경우에만 `c` 표현 싱글바이트 ASCII 소문자 영어 글자: 0x61\<\=`c`\<\= 0x7A.|  
  
 **코드 페이지 932 관련**  
  
 다음 루틴 코드 페이지 932에 적용 됩니다.  
  
|루틴|테스트 조건 \(코드 페이지 932만\)|  
|--------|----------------------------|  
|[\_ismbchira, \_ismbchira\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|더블 바이트 히라가나: 0x829F\<\=`c`\<\= 0x82F1.|  
|[\_ismbckata, \_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|더블 바이트 가타카나: 0x8340\<\=`c`\<\= 0x8396.|  
|[\_ismbcl0, \_ismbcl0\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS non\-Kanji: 0x8140\<\=`c`\<\=0x889E.|  
|[\_ismbcl1, \_ismbcl1\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS level\-1: 0x889F\<\=`c`\<\=0x9872.|  
|[\_ismbcl2, \_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS level\-2: 0x989F\<\=`c`\<\=0xEA9E.|  
  
 `_ismbcl0`, `_ismbcl1` 과 `_ismbcl2` 은 선행하는 표가 묘사된 테스트 조건에 일치하는 지정된 값 `c` 을 검사하지만, `c` 이 유효한 멀티 바이트 문자임을 검사하지 않습니다.  하위 바이트 0xFF, 0x00 – 0x7F 0x3F, 0xFD – 범위에는 이러한 함수 문자 테스트 조건에 맞는 것을 나타내는 0이 아닌 값을 반환합니다.  정의된 벌티 바이트인지 테스트하는 [\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) 사용하세요.  
  
 **END 코드 페이지 932 관련**  
  
## 참고 항목  
 [문자 분류](../c-runtime-library/character-classification.md)   
 [is, isw 루틴](../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 루틴](../c-runtime-library/ismbb-routines.md)