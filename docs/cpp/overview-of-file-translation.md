---
title: "파일 변환 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파일 변환[C++], 파일 변환 정보"
  - "파일[C++], 변환"
  - "변환 단계 처리"
  - "프로그램[C++], 어휘 규칙"
  - "변환[C++]"
  - "변환 단계"
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 파일 변환 개요
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C 프로그램과 같은 C\+\+ 프로그램은 하나 이상의 파일로 구성됩니다.  이러한 각 파일은 다음 개념적 순서로 변환됩니다. 실제 순서는 "as if" 규칙을 따릅니다. 변환은 이러한 단계를 수행한 것처럼 발생해야 합니다.  
  
1.  어휘 토큰화.  문자 매핑 및 삼중자 처리, 줄 스플라이스 및 토큰화는 이 변환 단계에서 수행됩니다.  
  
2.  전처리.  이 변환 단계는 `#include` 지시문에 의해 참조된 보조 소스 파일을 가져와 "stringizing" 및 "charizing" 지시문을 처리하고 토큰 붙여넣기 및 매크로 확장을 수행합니다. 자세한 내용은 *전처리기 참조*의 [전처리기 지시문](../preprocessor/preprocessor-directives.md)을 참조하십시오.  전처리 단계의 결과는 함께 "변환 단위"를 정의하는 토큰 시퀀스입니다.  
  
     전처리기 지시문은 항상 숫자 기호\(**\#**\) 문자로 시작합니다. 즉, 줄의 첫 비공백 문자가 숫자 기호여야 합니다.  하나의 전처리기 지시문만 지정된 줄에 나타날 수 있습니다.  예를 들면 다음과 같습니다.  
  
    ```  
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3.  코드 생성.  이 변환 단계는 전처리 단계에서 생성된 토큰을 사용하여 개체 코드를 생성합니다.  
  
     이 단계 중 소스 코드의 구문 및 의미 체계 검사가 수행됩니다.  
  
 자세한 내용은 *전처리기 참조*의 [변환 단계](../preprocessor/phases-of-translation.md)를 참조하십시오.  
  
 C\+\+ 전처리기는 ANSI C 전처리기의 엄격한 상위 집합이지만 몇 가지 점에서 다릅니다.  다음 목록에서는 ANSI C 전처리기와 C\+\+ 전처리기의 여러 가지 차이점을 설명합니다.  
  
-   한 줄로 된 주석이 지원됩니다.  자세한 내용은 [주석](../cpp/comments-cpp.md)을 참조하십시오.  
  
-   미리 정의된 매크로인 **\_\_cplusplus**는 C\+\+에 대해서만 정의됩니다.  자세한 내용은 *전처리기 참조*의 [미리 정의된 매크로](../preprocessor/predefined-macros.md)를 참조하십시오.  
  
-   C 전처리기는 C\+\+ 연산자인 **.\***, **–\>\*** 및 `::`을 인식하지 않습니다.  연산자에 대한 자세한 내용은 [연산자](../cpp/cpp-built-in-operators-precedence-and-associativity.md) 및 [식](../cpp/expressions-cpp.md)을 참조하십시오.  
  
## 참고 항목  
 [어휘 규칙](../cpp/lexical-conventions.md)