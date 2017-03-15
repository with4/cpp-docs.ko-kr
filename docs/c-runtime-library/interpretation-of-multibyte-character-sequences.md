---
title: "멀티바이트 문자 시퀀스 해석 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MBCS[C++], 로캘 코드 페이지"
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 멀티바이트 문자 시퀀스 해석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft 런타임 라이브러리에서 대부분의 멀티바이트 문자 루틴이 멀티바이트 코드 페이지에 대한 멀티 바이트 문자 시퀀스를 인식합니다.  출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  
  
### 로캘\-종속 멀티바이트 루틴  
  
|루틴|기능|  
|--------|--------|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|멀티 바이트 문자의 바이트의 수를 반환하고 유효성 검사를 합니다.|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|멀티 바이트\-문자 문자열: 문자열의 각 문자를 검사합니다; 문자열의 길이를 반환합니다.  와이드 문자 문자열: 문자열의 길이를 반환합니다.|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|멀티 바이트의 문자 시퀀스를 해당 와이드 문자 시퀀스로 변환합니다.|  
|[mbtowc, \_mbtowc\_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|멀티 바이트 문자를 해당 와이드 문자로 변환합니다.|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|해당 멀티 바이트 문자의 시퀀스로 와이드 문자의 시퀀스를 변환합니다.|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|와이드 바이트 문자를 해당 멀티바이트 문자로 변환합니다.|  
  
## 참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)