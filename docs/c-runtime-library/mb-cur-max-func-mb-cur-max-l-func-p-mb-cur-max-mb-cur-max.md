---
title: "___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max | Microsoft Docs"
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
  - "___mb_cur_max_l_func"
  - "__p___mb_cur_max"
  - "___mb_cur_max_func"
  - "__mb_cur_max"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___mb_cur_max_func"
  - "___mb_cur_max_l_func"
  - "__p___mb_cur_max"
  - "__mb_cur_max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___mb_cur_max_func"
  - "___mb_cur_max_l_func"
  - "__mb_cur_max"
  - "__p___mb_cur_max"
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

내부 CRT 함수입니다.  현재 또는 지정된 로캘에 대한 멀티바이트 문자의 최대 바이트 수를 검색합니다.  
  
## 구문  
  
```cpp  
int ___mb_cur_max_func(void); int ___mb_cur_max_l_func(_locale_t locale); int * __p___mb_cur_max(void); #define __mb_cur_max (___mb_cur_max_func())  
```  
  
#### 매개 변수  
 로캘\(locale\)  
 결과를 검색할 로캘 구조입니다.  이 값이 null이면 현재 스레드 로캘이 사용됩니다.  
  
## 반환 값  
 현재 스레드 로캘 또는 지정된 로캘에 대한 멀티바이트 문자의 최대 바이트 수입니다.  
  
## 설명  
 CRT가 스레드 로컬 저장소에서 [MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md) 매크로의 현재 값을 검색하는 데 사용하는 내부 함수입니다.  사용자 코드에서는 이식성을 위해 `MB_CUR_MAX` 매크로를 사용하는 것이 좋습니다.  
  
 `__mb_cur_max` 매크로는 `___mb_cur_max_func()` 함수를 호출하는 편리한 방법입니다.  `__p___mb_cur_max` 함수는 Visual C\+\+ 5.0 및 이전 버전과의 호환성을 위해 정의되었습니다.  
  
 내부 CRT 함수는 구현과 관련되어 있으며 각 릴리스 시 변경될 수 있습니다.  따라서 사용자 코드에는 사용하지 않는 것이 좋습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h\>, \<stdlib.h\>|  
  
## 참고 항목  
 [MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md)