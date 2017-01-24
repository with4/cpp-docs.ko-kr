---
title: "wctype | Microsoft Docs"
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
  - "wctype"
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
apitype: "DLLExport"
f1_keywords: 
  - "wctype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wctype 함수"
  - "와이드 문자"
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자 코드에 대한 분류 규칙을 결정합니다.  
  
## 구문  
  
```  
wctype_t wctype(  
   const char * property   
);  
```  
  
#### 매개 변수  
 `property`  
 String 속성  
  
## 반환 값  
 현재 로캘의 `LC_CTYPE` 카테고리가 속성 문자열 `property` 과 일치하는 이름의 분류 규칙을 지정하지 않는 경우, 함수는 0을 반환합니다.  그렇지 않으면, [towctrans](../../c-runtime-library/reference/towctrans.md) 에 대한 후속 호출에 두 번째 인수로 사용하기에 적합한 0이 아닌 값을 반환합니다.  
  
## 설명  
 함수는 와이드 문자 코드에 대한 분류 규칙을 결정합니다.  호출의 다음 쌍은 모든 지역에서 동일한 동작입니다. \(하지만 구현은 "C"로케일로 추가 분류 규칙을 정의 할 수 있습니다\) :  
  
|Function|Same as|  
|--------------|-------------|  
|`iswalnum(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alnum" ) )`|  
|`iswalpha(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alpha" ) )`|  
|`iswcntrl(`  `c`  `)`|`iswctype(`  `c` `, wctype( "cntrl" ) )`|  
|`iswdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "digit" ) )`|  
|`iswgraph(`  `c`  `)`|`iswctype(`  `c` `, wctype( "graph" ) )`|  
|`iswlower(`  `c`  `)`|`iswctype(`  `c` `, wctype( "lower" ) )`|  
|`iswprint(`  `c`  `)`|`iswctype(`  `c` `, wctype( "print" ) )`|  
|`iswpunct(`  `c`  `)`|`iswctype(`  `c` `, wctype( "punct" ) )`|  
|`iswspace(`  `c`  `)`|`iswctype(`  `c` `, wctype( "space" ) )`|  
|`iswupper(`  `c`  `)`|`iswctype(`  `c` `, wctype( "upper" ) )`|  
|`iswxdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "xdigit" ) )`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wctype`|\<wctype.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)