---
title: "인라인 어셈블리에서 C++ 함수 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm 키워드[C++], 함수 호출"
  - "함수 호출, C++ 함수"
  - "함수 호출, 인라인 어셈블리"
  - "함수[C++], 인라인 어셈블리에서 호출"
  - "인라인 어셈블리, 함수 호출"
  - "Visual C++, 함수"
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 어셈블리에서 C++ 함수 호출
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `__asm` 블록은 오버로드되지 않은 전역 C\+\+ 함수만 호출할 수 있습니다.  오버로드된 전역 C\+\+ 함수 또는 C\+\+ 멤버 함수를 호출하면 컴파일러에서 오류가 발생합니다.  
  
 **extern "C"** 링크로 선언된 함수를 호출할 수도 있습니다.  모든 표준 헤더 파일이 **extern "C"** 링크가 있는 라이브러리 함수를 선언하기 때문에 C\+\+ 프로그램 내에 있는 `__asm` 블록이 C 라이브러리 함수를 호출할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [인라인 어셈블러](../../assembler/inline/inline-assembler.md)