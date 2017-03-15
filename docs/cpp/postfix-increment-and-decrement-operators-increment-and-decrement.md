---
title: "후위 증가 및 감소 연산자: ++ 및 -- | Microsoft Docs"
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
  - "--"
  - "++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-- 연산자, 후위 감소 연산자"
  - "++ 연산자, 후위 증가 연산자"
  - "감소 연산자"
  - "감소 연산자, 구문"
  - "증가 연산자, 구문"
  - "멤버 선택 연산자"
  - "연산자[C++], 후위"
  - "후위 연산자"
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 후위 증가 및 감소 연산자: ++ 및 --
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
      postfix-expression   
      ++  
postfix-expression ––  
```  
  
## 설명  
 C\+\+는 전위\/후위 증가 및 감소 연산자를 제공합니다. 이 단원에서는 후위 증가 및 감소 연산자에 대해서만 설명합니다. 자세한 내용은 [전위 증가 및 감소 연산자](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)를 참조하십시오. 후위 표기법과 전위 표기법의 차이는 후위 표기법에서는 연산자가 후위 식 뒤에 표시되지만 전위 표기법에서는 연산자가 식 앞에 표시된다는 점입니다. 다음 예제에서는 후위 증가 연산자를 보여 줍니다.  
  
```  
i++;  
```  
  
 후위 증가 연산자\(`++`\)를 적용하면 피연산자 값이 적절한 형식의 단위로 한 단위씩 증가하게 됩니다.  마찬가지로 후위 감소 연산자\(**––**\)를 적용하면 피연산자의 값은 적절한 형식의 단위로 한 단위씩 감소하게 됩니다.  
  
 주의해야 할 점은 후위 증가 또는 감소 식은 각 연산자를 적용하기 **전에** 식의 값으로 계산된다는 것입니다.  증가 또는 감소 연산은 피연산자가 계산된 **후에** 진행됩니다.  이 문제는 후위 증가나 감소 연산이 더 큰 수식의 컨텍스트에서 진행할 경우에만 발생합니다.  
  
 후위 연산자가 함수 인수에 적용될 때 해당 인수의 값은 함수에 전달된 후에만 증가하거나 감소됩니다.  자세한 내용은 C\+\+ 표준의 1.9.17 단원을 참조하십시오.  
  
 후위 증가 연산자를 **long** 형식 개체의 배열 포인터에 적용하면 포인터의 내부 표현에 4가 실제로 추가됩니다.  이 동작은 이전에 *n*번째 배열 요소를 참조한 포인터가 \(*n*\+1\)번째 요소를 참조하도록 합니다.  
  
 후위 증가 및 감소 연산자의 피연산자는 **const** 형식이 아닌 산술 또는 포인터 형식의 변경 가능한 l\-value여야 합니다.  결과의 형식은 후위 식 형식과 동일하지만 l\-value가 될 수는 없습니다.  
  
 또한 후위 증가 연산자의 피연산자의 형식은 `bool`이 될 수도 있는데, 이 경우 피연산자는 **true**로 계산 설정됩니다.  후위 감소 연산자의 피연산자의 형식은 `bool`이 될 수 없습니다.  
  
 다음 코드에서는 후위 증가 연산자에 대해 설명합니다.  
  
```  
// expre_Postfix_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 10;  
   cout << i++ << endl;  
   cout << i << endl;  
}  
```  
  
 후위 증가 및 감소 연산은 열거형 형식에서 지원되지 않습니다.  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## 참고 항목  
 [후위 식](../cpp/postfix-expressions.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 후위 증가 및 감소 연산자](../c-language/c-postfix-increment-and-decrement-operators.md)