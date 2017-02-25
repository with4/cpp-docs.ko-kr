---
title: "Variadic 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Variadic 매크로[C++]"
  - "__VA_ARGS__ variadic 매크로 지정자"
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Variadic 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Variadic 매크로 함수와 비슷한 매크로는 가변 개수의 인수를 포함합니다.  
  
## 설명  
 Variadic 매크로 사용하려면, 줄임표는 매크로 정의에서 최종 형식 인수로 지정되고 대체 식별자 `__VA_ARGS__` 는 삽입 추가 인수를 정의하는 데에 사용될 수 있습니다.  `__VA_ARGS__` 는 줄임표, 그 사이 쉼표와 일치하는 모든 인수로 대체 됩니다.  
  
 C 표준에서는 매크로가 쉼표가 뒤에 오는 식으로 확인되지 않게 하기 위해 적어도 하나의 인수가 줄임표로 전달되어야 하도록 지정합니다.  Visual C\+\+ 구현에서 줄임표에 전달된 인수가 없는 경우 뒤에 오는 쉼표가 숨겨집니다.  
  
## 예제  
  
```cpp  
// variadic_macros.cpp  
#include <stdio.h>  
#define EMPTY  
  
#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }  
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }  
#define CHECK3(...) { printf(__VA_ARGS__); }  
#define MACRO(s, ...) printf(s, __VA_ARGS__)  
  
int main() {  
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");  
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print  
  
    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print  
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");  
  
    // always invokes printf in the macro  
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");  
  
    MACRO("hello, world\n");  
  
    MACRO("error\n", EMPTY); // would cause error C2059, except VC++   
                             // suppresses the trailing comma  
}  
```  
  
## Output  
  
```  
here are some varargs1(1)  
here are some varargs2(4)  
here are some varargs3(5)  
hello, world  
error  
  
```  
  
## 참고 항목  
 [매크로](../preprocessor/macros-c-cpp.md)