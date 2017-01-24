---
title: "sizeof 연산자 (C) | Microsoft Docs"
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
  - "sizeof"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "sizeof 연산자"
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sizeof 연산자 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`sizeof` 연산자는 피연산자 형식의 개체를 저장하기 위해 필요한 저장소 공간\(바이트\)을 제공합니다.  이 연산자를 사용하면 프로그램에서 컴퓨터 종속 데이터 크기를 지정하지 않아도 됩니다.  
  
## 구문  
  
```  
  
      sizeof unary-expression  
sizeof ( type-name )  
```  
  
## 설명  
 이 피연산자는 *unary\-expression* 식별자이거나 괄호로 묶은 형식 지정자인 형식 캐스트 식입니다.  *unary\-expression*은 비트 필드 개체, 불완전한 형식 또는 함수 지정자를 나타낼 수 없습니다.  결과는 부호 없는 정수 계열 상수입니다.  표준 헤더 STDDEF.H에서는 이 형식을 **size\_t**로 정의합니다.  
  
 `sizeof` 연산자를 배열 식별자에 적용하면 해당 결과는 배열 식별자가 나타내는 포인터의 크기가 아닌 전체 배열의 크기입니다.  
  
 `sizeof` 연산자를 구조체 또는 공용 구조체 형식 이름 또는 구조체 또는 공용 구조체 형식의 식별자에 적용하면 해당 결과는 내부 및 후행 여백을 포함하는 구조체 또는 공용 구조체의 바이트 수입니다.  이 크기는 메모리 경계에서 구조체 또는 공용 구조체의 멤버를 정렬하는데 사용되는 내부 및 후행 공백을 포함할 수 있습니다.  따라서 해당 결과는 개별 멤버의 저장소 요구 사항을 추가하여 계산된 크기와 일치하지 않을 수도 있습니다.  
  
 크기가 지정되지 않은 배열이 구조체의 마지막 요소인 경우 `sizeof` 연산자는 배열 없는 구조체의 크기를 반환합니다.  
  
```  
buffer = calloc(100, sizeof (int) );  
```  
  
 이 예제에서는 `sizeof` 연산자를 사용하여 컴퓨터 간에 서로 다른 `int`의 크기를 `calloc`이라고 하는 런타임 함수에 대한 인수로 전달합니다.  함수에서 반환되는 값은 `buffer`에 저장됩니다.  
  
```  
static char *strings[] ={  
          "this is string one",  
          "this is string two",  
          "this is string three",  
         };  
const int string_no = ( sizeof strings ) / ( sizeof strings[0] );   
```  
  
 이 예제에서 `strings`는 `char`에 대한 포인터의 배열입니다.  포인터 수는 배열의 요소 개수이지만 지정되지 않습니다.  `sizeof` 연산자를 사용하여 배열의 요소 수를 계산하면 포인터 수를 쉽게 확인할 수 있습니다.  **const** 정수 값 `string_no`는 이 수로 초기화됩니다.  이는 **const** 값이기 때문에 `string_no`는 수정할 수 없습니다.  
  
## 참고 항목  
 [C\+\+ 연산자](../misc/cpp-operators.md)