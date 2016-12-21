---
title: "SBCS 및 MBCS 데이터 형식 | Microsoft Docs"
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
  - "MBCS"
  - "SBCS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SBCS 및 MBCS 데이터 형식"
  - "데이터 형식[C], MBCS 및 SBCS"
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# SBCS 및 MBCS 데이터 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

오직 하나의 멀티 바이트 문자 또는 멀티 바이트 문자의 한 바이트만을 처리하는 모든 Microsoft `MBCS` 런타임 라이브러리 루틴은 `unsigned` `int` 인수를 기대합니다. \(0x00 \<\= 문자 값 \<\=0xFFFF이고 0x00 \<\= 바이트 값 \<\= 0xFF인 위치\)  멀티 바이트 또는 문자열 컨텍스트의 문자를 처리하는 `MBCS` 루틴은 멀티 바이트 문자 문자열이 `unsigned` `char` 포인터로 표현되는 것을 기대합니다.  
  
> [!CAUTION]
>  멀티 바이트 문자의 각 바이트는 8비트 `char`로 표현될 수 있습니다.  그러나, 값이 0x7F보다 큰 `char` 형식의 `SBCS` 또는 `MBCS` 싱글바이트 문자는 음수입니다.  그러한 문자가 직접적으로 `int` 또는 `long`로 변환될 때, 결과는 컴파일러에 의해 부호 확장되고 그러므로 예기치 않은 결과를 만들 수 있습니다.  
  
 따라서 멀티 바이트 문자의 바이트는 8비트 `unsigned char`로 표현하는 것이 가장 좋습니다.  또는, 음수의 결과를 피하기 위해서는, 단순히 `char` 형식의 단일 바이트 문자를 `int` 또는 `long` 형식으로 변환하기 전에 `unsigned char`로 변환합니다.  
  
 일부 `SBCS` 문자열 처리 함수는 \(부호 있는\) `char*` 매개 변수를 사용하기 때문에 `_MBCS`가 정의되면 형식이 일치하지 않는다는 컴파일러 경고가 표시됩니다.  이 경고를 피하기 위한 세 가지 방법을 효율 순으로 나열합니다.  
  
1.  TCHAR.H에 형식이 안전한 인라인 함수 썽크를 사용합니다.  이것은 기본적인 동작입니다.  
  
2.  명령줄에서 `_MB_MAP_DIRECT` 를 정의하여 TCHAR.H에 직접 매크로를 사용합니다.  이 경우 수동으로 형식을 일치시켜야 합니다.  속도가 가장 빠른 방법이지만 형식이 안전하지 않습니다.  
  
3.  TCHAR.H에 형식이 안전한 정적 링크 라이브러리 함수 썽크를 사용합니다.  이렇게 하려면 명령줄에서 상수 `_NO_INLINING`을 정의합니다.  속도가 가장 느린 방법이지만 형식은 가장 안전합니다.  
  
## 참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)