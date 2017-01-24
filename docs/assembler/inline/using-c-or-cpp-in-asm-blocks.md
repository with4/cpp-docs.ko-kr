---
title: "__asm 블록에서 C 또는 C++ 사용 | Microsoft Docs"
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
  - "주석, __asm 블록"
  - "상수, __asm 블록"
  - "인라인 어셈블리, C/C++ 문과 명령 혼용"
  - "매크로, __asm 블록"
  - "전처리기 지시문"
  - "전처리기 지시문, __asm 블록에서 사용됨"
  - "전처리기, 지시문"
  - "기호, __asm 블록"
  - "형식 이름, __asm 블록에서 사용됨"
  - "형식 정의 이름, __asm 블록에서 사용됨"
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __asm 블록에서 C 또는 C++ 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 인라인 어셈블리 명령은 C 또는 C\+\+ 문과 함께 사용할 수 있으므로 C 또는 C\+\+ 변수를 이름으로 참조하고 이러한 언어의 다른 많은 요소를 사용할 수 있습니다.  
  
 `__asm` 블록은 다음 언어 요소를 사용할 수 있습니다.  
  
-   레이블과 변수 및 함수 이름을 포함하는 기호  
  
-   기호화된 상수와 `enum` 멤버를 포함하는 상수  
  
-   매크로 및 전처리기 지시문  
  
-   주석\(**\/\* \*\/** 및 **\/\/**\)  
  
-   형식 이름\(MASM 형식이 올바를 때마다\)  
  
-   구조체 또는 공용 구조체 멤버를 지정하기 위해 일반적으로 **PTR** 및 **TYPE** 등 연산자와 함께 사용되는 `typedef` 이름  
  
 `__asm` 블록 내에서 C 표기법 또는 어셈블러 기수 표기법과 함께 정수 상수\(예: 0x100 및 100h는 동일\)를 지정할 수 있습니다.  이를 통해 C에서 \(`#define`을 사용하여\) 상수를 정의한 다음 C 또는 C\+\+ 모두와 프로그램의 어셈블리 부분에서 사용할 수 있습니다.  a 0과 함께 이전 상수에 의해 8진수에서 상수를 지정할 수도 있습니다.  예를 들어, 0777은 8진수 상수를 지정합니다.  
  
## 추가 정보  
  
-   [\_\_asm 블록에서 연산자 사용](../../assembler/inline/using-operators-in-asm-blocks.md)  
  
-   [\_\_asm 블록에서 C 또는 C\+\+ 기호 사용](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)  
  
-   [\_\_asm 블록에서 C 또는 C\+\+ 데이터 액세스](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)  
  
-   [인라인 어셈블리로 함수 작성](../../assembler/inline/writing-functions-with-inline-assembly.md)  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [인라인 어셈블러](../../assembler/inline/inline-assembler.md)