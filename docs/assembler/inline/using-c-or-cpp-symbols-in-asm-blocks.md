---
title: "__asm 블록에서 C 또는 C++ 기호 사용 | Microsoft Docs"
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
  - "__asm 키워드[C++], C/C++ 요소"
  - "__asm 키워드[C++], 구문"
  - "기호, __asm 블록"
  - "Visual C, __asm 블록의 기호"
  - "Visual C++, __asm 블록"
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __asm 블록에서 C 또는 C++ 기호 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 관련  
 `__asm`블록 블록을 표시할 위치 범위에 있는 모든 C 또는 c \+ \+ 기호를 참조할 수 있습니다.  \(C와 c \+ \+ 기호는 변수 이름, 함수 이름 및 레이블. 기호 상수 되지 않는 이름, 또는  `enum`멤버입니다.  수 없는 c \+ \+ 멤버 함수를 호출 합니다.\)  
  
 C 및 c \+ \+ 기호를 사용 하는 몇 가지 제한이 적용 됩니다.  
  
-   각 어셈블리 언어 명령문 한 C 또는 c \+ \+ 기호를 포함할 수 있습니다.  여러 기호에만 동일한 어셈블리 명령에 나타날 수 있습니다  **길이**,  **유형**, 및  **크기** 식입니다.  
  
-   함수에서 참조 되는  `__asm`블록 \(프로토타입\) 프로그램 앞부분에 선언 해야 합니다.  그렇지 않으면 컴파일러가 구별할 수 없습니다 함수 이름과 이름표는  `__asm`블록.  
  
-   `__asm`블록 \(케이스\)에 관계 없이 예약 된 MASM 단어 철자를 사용 하 여 C 또는 c \+ \+ 기호를 사용할 수 없습니다.  와 같은 MASM 예약 된 단어는 명령 이름  **PUSH** SI 같은 이름을 등록 하 고.  
  
-   구조체 및 공용 구조체 태그를 인식 하지 못하는  `__asm`블록.  
  
 **Microsoft 특정 끝**  
  
## 참고 항목  
 [\_\_asm 블록에서 C 또는 C\+\+ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)