---
title: "1의 보수 연산자: ~ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "~"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ 연산자, 구문"
  - "비트 보수 연산자"
  - "보수 연산자"
  - "1의 보수 연산자"
  - "물결표(~) 1의 보수 연산자"
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1의 보수 연산자: ~
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
~ cast-expression  
```  
  
## 설명  
 "비트 보수" 연산자라고도 하는 1의 보수 연산자\(`~`\)는 해당 피연산자의 비트 1의 보수를 생성합니다.  즉, 피연산자의 1인 모든 비트는 결과적으로 0입니다.  반대로 피연산자의 0인 모든 비트는 결과적으로 1입니다.  1의 보수 연산자의 피연산자는 정수 계열 형식이어야 합니다.  
  
## ~에 대한 연산자 키워드  
 `compl` 연산자는 `~`에 해당하는 텍스트입니다.  프로그램에서 `compl` 연산자에 액세스하는 두 가지 방법이 있습니다. 헤더 파일 `iso646.h`를 포함하거나 [\/Za](../build/reference/za-ze-disable-language-extensions.md)로 컴파일하는 것입니다.  
  
## 예제  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 이 예제에서 `y`에 할당된 새 값은 부호 없는 값인 0xFFFF의 1의 보수이거나 0x0000입니다.  
  
 정수 계열 확장은 정수 계열 피연산자에서 수행되며, 결과 형식은 피연산자가 확장되는 형식입니다.  확장 수행 방법에 대한 자세한 내용은 [정수 계열 확장](../misc/integral-promotions.md)을 참조하십시오.  
  
## 참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [단항 산술 연산자](../c-language/unary-arithmetic-operators.md)