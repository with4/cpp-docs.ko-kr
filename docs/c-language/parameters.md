---
title: "매개 변수 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "... 줄임표"
  - "인수[C++], 함수"
  - "줄임표(...), 매개 변수"
  - "함수 인수, 매개 변수와 비교"
  - "함수 매개 변수"
  - "함수 매개 변수, 구문"
  - "함수[C++], 매개 변수"
  - "매개 변수[C++]"
  - "매개 변수[C++], 함수"
ms.assetid: 8f2b8026-78b5-4e21-86a3-bf0f91f05689
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 매개 변수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인수는 함수 호출을 통해 함수에 전달되는 값의 이름입니다.  매개 변수는 함수가 수신할 수 있는 값입니다.  함수 프로토타입에서 함수 이름 뒤의 괄호에는 함수의 전체 매개 변수 및 해당 형식 목록이 포함됩니다.  매개 변수 선언은 형식, 크기 및 매개 변수에 저장된 값의 식별자를 지정합니다.  
  
## 구문  
 *function\-definition*:  
 *declaration\-specifiers*  opt *attribute\-seq* opt *declarator declaration\-list* opt *compound\-statement*  
  
 \/\* *attribute\-seq*는 Microsoft 전용임 \*\/  
  
 *declarator*:  
 *pointer*  opt *direct\-declarator*  
  
 *direct\-declarator*:\/\* 함수 선언자 \*\/  
 *direct\-declarator*  **\(**  *parameter\-type\-list*  **\)** \/\* 새로운 스타일의 선언자 \*\/  
  
 *parameter\-type\-list*: \/\* 매개 변수 목록 \*\/  
 *parameter\-list*  
  
 *parameter\-list*  **,...**  
  
 *parameter\-list*:  
 *parameter\-declaration*  
  
 *parameter\-list*  **,**  *parameter\-declaration*  
  
 *parameter\-declaration*:  
 *declaration\-specifiers declarator*  
  
 *declaration\-specifiers abstract\-declarator*  opt  
  
 *parameter\-type\-list*는 쉼표로 구분된 매개 변수 선언 시퀀스입니다.  매개 변수 목록에 있는 각 매개 변수 형식은 다음과 같습니다.  
  
```  
[register]  type-specifier [declarator]   
```  
  
 **auto** 특성을 사용하여 선언된 함수 매개 변수는 오류를 생성합니다.  매개 변수 식별자는 함수 본문에 사용되어 함수에 전달된 값을 참조합니다.  프로토타입에서 매개 변수 이름을 지정할 수 있지만 선언 끝에서 이름이 범위를 벗어납니다.  따라서 함수 정의에서 같거나 다른 방식으로 매개 변수 이름을 지정할 수 있습니다.  함수 본문의 가장 바깥쪽 블록에서 이 식별자를 다시 정의할 수 있지만 매개 변수 목록이 바깥쪽 블록인 것처럼 내부의 중첩 블록에서 다시 정의할 수 있습니다.  
  
 이 예제에 표시된 대로 *parameter\-type\-list*의 각 식별자는 적합한 형식 식별자 뒤에 와야 합니다.  
  
```  
void new( double x, double y, double z )  
{  
    /* Function body here */  
}  
```  
  
 매개 변수 목록에 매개 변수가 하나 이상 있을 경우 목록 끝에 쉼표 1개와 마침표 3개가 차례로 올 수 있습니다\(**, ...**\).  "줄임표 표기법"이라고 하는 이 생성은 가변적인 개수의 인수가 함수에 사용됨을 나타냅니다. 자세한 내용은 [가변적인 개수의 인수를 사용하여 호출](../c-language/calls-with-a-variable-number-of-arguments.md)을 참조하십시오. 그러나 함수 호출에는 마지막 쉼표 앞에 있는 매개 변수만큼 인수가 있어야 합니다.  
  
 함수에 인수가 전달되지 않을 경우 `void` 키워드에 의해 매개 변수 목록이 바뀝니다.  이때 `void` 사용은 형식 지정자로 사용하는 것과는 다릅니다.  
  
 줄임표 표기법 사용을 포함하여 매개 변수의 순서와 형식은 모든 함수 선언\(있을 경우\) 및 함수 정의에서 동일해야 합니다.  일반적인 산술 변환 후 인수 형식이 해당 매개 변수의 형식과 할당 호환이 되어야 합니다. 산술 변환에 대한 자세한 내용은 [일반적인 산술 변환](../c-language/usual-arithmetic-conversions.md)을 참조하십시오. 줄임표 뒤의 인수는 확인되지 않습니다.  매개 변수는 기본, 구조체, 공용 구조체, 포인터 또는 배열 형식을 가질 수 있습니다.  
  
 필요할 경우 컴파일러가 매개 변수 및 인수마다 독립적으로 일반적인 산술 변환을 수행합니다.  변환 후 매개 변수는 `int`보다 짧아지지 않으며 매개 변수 형식이 명시적으로 프로토타입에 **float**로 지정되지 않을 경우 매개 변수가 **float** 형식을 가질 수 없습니다.  예를 들어, 매개 변수를 `char`로 선언하면 `int`로 선언하는 것과 같은 효과를 가진다는 의미입니다.  
  
## 참고 항목  
 [C 함수 정의](../c-language/c-function-definitions.md)