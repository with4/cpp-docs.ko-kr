---
title: "로캘 범주 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LC_MAX"
  - "LC_MIN"
  - "LC_MONETARY"
  - "LC_TIME"
  - "LC_NUMERIC"
  - "LC_COLLATE"
  - "LC_CTYPE"
  - "LC_ALL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "LC_ALL 상수"
  - "LC_COLLATE 상수"
  - "LC_CTYPE 상수"
  - "LC_MAX 상수"
  - "LC_MIN 상수"
  - "LC_MONETARY 상수"
  - "LC_NUMERIC 상수"
  - "LC_TIME 상수"
  - "로캘 상수"
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 로캘 범주
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <locale.h>  
  
```  
  
## 설명  
 로캘 범주는 프로그램의 로캘 정보의 어느 부분이 사용될 것인지를 지정하기 위하여 지역 루틴에 의해서 사용되는 매니페스트 상수입니다.  로캘은 지역화될 수 있는 프로그램의 특정 측면을 위한 인근\(또는 나라\/지역\)을 참조합니다.  로캘 종속 범주는 예를 들어, 날짜 형식 지정 또는 통화 값의 형식 표시가 포함됩니다.  
  
|로캘 범주|영향 받는 프로그램의 부분|  
|-----------|--------------------|  
|`LC_ALL`|모든 특정 로캘 행동 \(모든 범주\)|  
|`LC_COLLATE`|`strcoll` 및 `strxfrm` 함수의 동작|  
|`LC_CTYPE`|문자 처리 함수의 동작\(영향을 받지 않는 **isdigit**, `isxdigit`, `mbstowcs`, `mbtowc`을 제외\)|  
|`LC_MAX`|`LC_TIME`와 동일|  
|`LC_MIN`|`LC_ALL`와 동일|  
|`LC_MONETARY`|`localeconv` 함수에 의해서 반환되는 monetary\-형식 정보|  
|`LC_NUMERIC`|형식이 지정 된 출력 루틴\(예를 들어 `printf`과 같은\), 데이터 변환 루틴, `localeconv`에 의해 반환된 비통화 서식 정보에 대한 10진 소수점 문자|  
|`LC_TIME`|`strftime` 함수의 동작|  
  
 예제는 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  
  
## 참고 항목  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 함수](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [전역 상수](../c-runtime-library/global-constants.md)