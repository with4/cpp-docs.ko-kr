---
title: "___lc_locale_name_func | Microsoft Docs"
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
  - "___lc_locale_name_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___lc_locale_name_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_locale_name_func"
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ___lc_locale_name_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

내부 CRT 함수입니다.  스레드의 현재 로캘 이름을 검색합니다.  
  
## 구문  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## 반환 값  
 스레드의 현재 로캘 이름이 포함된 문자열에 대한 포인터입니다.  
  
## 설명  
 `___lc_locale_name_func`는 다른 CRT 함수가 CRT 데이터의 스레드 로컬 저장소에서 현재 로캘 이름을 가져오기 위해 사용하는 내부 CRT 함수입니다.  [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md) 함수 또는 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 함수를 사용하면 이 정보를 사용할 수 있습니다.  
  
 내부 CRT 함수는 구현과 관련되어 있으며 각 릴리스 시 변경될 수 있습니다.  따라서 사용자 코드에는 사용하지 않는 것이 좋습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`___lc_locale_name_func`|crt\\src\\setlocal.h|  
  
## 참고 항목  
 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)