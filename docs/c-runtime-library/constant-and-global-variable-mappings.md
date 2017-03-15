---
title: "상수 및 전역 변수 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_tenviron"
  - "_TEOF"
  - "_tfinddata_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tenviron 함수"
  - "_TEOF 형식"
  - "_tfinddata_t 함수"
  - "일반 텍스트 매핑"
  - "tenviron 함수"
  - "TEOF 형식"
  - "tfinddatat 함수"
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 상수 및 전역 변수 매핑
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이러한 일반 텍스트 상수, 전역 변수 및 표준 형식 매핑은 TCHAR.H에 정의 되고 `_UNICODE` 또는 `_MBCS` 상수가 프로그램에 정의 되어 있는지에 의존합니다.  
  
### 일반 텍스트, 상수 및 전역 변수 매핑  
  
|일반 텍스트\-개체 이름|SBCS \(\_UNICODE, \_MBCS not defined\)|\_MBCS 정의됨|\_UNICODE 정의됨|  
|-------------------|--------------------------------------------|----------------|-------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## 참고 항목  
 [일반 텍스트 매핑](../c-runtime-library/generic-text-mappings.md)   
 [데이터 형식 매핑](../c-runtime-library/data-type-mappings.md)   
 [루틴 매핑](../c-runtime-library/routine-mappings.md)   
 [샘플 일반 텍스트 프로그램](../c-runtime-library/a-sample-generic-text-program.md)   
 [일반 텍스트 매핑 사용](../c-runtime-library/using-generic-text-mappings.md)