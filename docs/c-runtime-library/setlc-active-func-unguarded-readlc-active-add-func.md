---
title: "___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___unguarded_readlc_active_add_func"
  - "___setlc_active_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ___setlc_active_func, ___unguarded_readlc_active_add_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용되지 않습니다.  CRT는 이진 호환성을 유지하기 위해서만 내부 함수를 내보냅니다.  
  
## 구문  
  
```cpp  
int ___setlc_active_func(void); int * ___unguarded_readlc_active_add_func(void);  
```  
  
## 반환 값  
 반환되는 값은 중요하지 않습니다.  
  
## 설명  
 내부 CRT 함수인 `___setlc_active_func` 및 `___unguarded_readlc_active_add_func`가 더 이상 사용되지 않더라도 이진 호환성을 유지하기 위해 CRT에서는 이러한 함수를 내보냅니다.  `___setlc_active_func`의 원래 용도는 현재 활성 호출 수를 `setlocale` 함수로 반환하는 것입니다.  `___unguarded_readlc_active_add_func`의 원래 용도는 로캘을 잠그지 않고 로캘을 참조하는 함수의 수를 반환하는 것이었습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|없음|  
  
## 참고 항목  
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)