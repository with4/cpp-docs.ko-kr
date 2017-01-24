---
title: "___lc_codepage_func | Microsoft Docs"
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
  - "___lc_codepage_func"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lc_codepage_func"
  - "___lc_codepage_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_codepage_func"
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ___lc_codepage_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

내부 CRT 함수입니다.  스레드의 현재 코드 페이지를 검색합니다.  
  
## 구문  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## 반환 값  
 스레드의 현재 코드 페이지입니다.  
  
## 설명  
 `___lc_codepage_func`는 다른 CRT 함수가 CRT 데이터의 스레드 로컬 저장소에서 현재 코드 페이지를 가져오는 데 사용하는 내부 CRT 함수입니다.  또한 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md) 함수를 사용하면 이 정보를 사용할 수 있습니다.  
  
 *코드 페이지*는 개별 문자에 대한 싱글바이트 또는 더블바이트 코드의 매핑입니다.  여러 코드 페이지에는 일반적으로 언어 또는 언어 그룹에 대해 사용자 지정된 여러 특수 문자가 들어 있습니다.  코드 페이지에 대한 자세한 내용은 [코드 페이지](../c-runtime-library/code-pages.md)를 참조하십시오.  
  
 내부 CRT 함수는 구현과 관련되어 있으며 각 릴리스 시 변경될 수 있습니다.  따라서 사용자 코드에는 사용하지 않는 것이 좋습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`___lc_codepage_func`|crt\\src\\setlocal.h|  
  
## 참고 항목  
 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)