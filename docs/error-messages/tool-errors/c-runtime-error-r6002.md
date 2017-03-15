---
title: "C 런타임 오류 R6002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6002"
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# C 런타임 오류 R6002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 지원이 로드되지 않았습니다.  
  
 필요한 부동 소수점 라이브러리가 링크되지 않았습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  보조 프로세서를 필요로 하는 \/FPi87 옵션을 사용하여 프로그램을 컴파일하거나 링크했으나 보조 프로세서가 설치되어 있지 않은 컴퓨터에서 실행했습니다.  
  
2.  `printf_s` 또는 `scanf_s` 함수에 대한 형식 문자열에 부동 소수점 형식 사양이 들어 있지만 프로그램에는 부동 소수점 값이나 변수가 들어 있지 않습니다.  
  
3.  컴파일러는 필요할 때에만 부동 소수점 지원을 로드하여 프로그램의 크기를 최소화하는데  형식 문자열에 들어 있는 부동 소수점 형식 사양을 검색할 수 없으므로 필요한 부동 소수점 루틴을 로드하지 않습니다.  
  
4.  부동 소수점 형식 사양에 일치하는 부동 소수점 인수를 사용하거나 프로그램의 한 부분에서 부동 소수점 할당을 수행합니다.  이렇게 하면 부동 소수점 지원이 로드됩니다.  
  
5.  여러 언어를 사용하는 프로그램에서 프로그램이 링크될 때 C 라이브러리가 FORTRAN 라이브러리보다 먼저 지정됩니다.  다시 링크하여 C 라이브러리를 마지막에 지정하십시오.