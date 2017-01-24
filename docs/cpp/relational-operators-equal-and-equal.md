---
title: "관계형 연산자: &lt;, &gt;, &lt;= 및 &gt;= | Microsoft Docs"
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
  - "<"
  - ">"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "< 연산자"
  - "<= 연산자"
  - "> 연산자"
  - ">= 연산자"
  - "보다 큼 연산자"
  - "크거나 같음 연산자"
  - "보다 작음 연산자"
  - "작거나 같음 연산자"
  - "관계형 연산자, 구문"
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 관계형 연산자: &lt;, &gt;, &lt;= 및 &gt;=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
        expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## 설명  
 이항 관계형 연산자는 다음과 같은 관계를 확인합니다.  
  
-   보다 작음\(**\<**\)  
  
-   보다 큼\(**\>**\)  
  
-   작거나 같음\(**\<\=**\)  
  
-   크거나 같음\(**\>\=**\)  
  
 관계형 연산자는 왼쪽에서 오른쪽으로 결합됩니다.  관계형 연산자의 두 피연산자는 산술 또는 포인터 형식이어야 하며,  `bool` 형식의 값을 생성합니다.  식의 관계가 false이면 반환 값은 **false**\(0\)이고, 그렇지 않으면 반환 값은 **true**\(1\)입니다.  
  
## 예제  
  
```  
// expre_Relational_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << "The true expression 3 > 2 yields: "  
         << (3 > 2) << endl  
         << "The false expression 20 < 10 yields: "  
         << (20 < 10) << endl;  
}  
```  
  
 스트림 삽입 연산자\(**\<\<**\)가 관계형 연산자보다 우선순위가 높기 때문에 위의 예제에 있는 식은 괄호로 묶여야 합니다.  따라서 괄호가 없는 첫 번째 식은 다음과 같이 평가됩니다.  
  
```  
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 [산술 변환](../misc/arithmetic-conversions.md)에서 다루는 일반적인 산술 변환은 산술 형식의 피연산자에 적용됩니다.  
  
## 포인터 비교  
 형식이 같은 개체의 포인터 2개를 비교할 때 프로그램의 주소 공간에서 가리키는 개체 위치에 따라 결과가 결정됩니다.  0 또는 void \* 형식의 포인터로 계산되는 상수 식과 포인터를 비교할 수도 있습니다.  void \* 형식의 포인터에 대해 포인터를 비교할 경우 암시적으로 다른 포인터가 void \* 형식으로 변환됩니다.  그런 다음 비교가 수행됩니다.  
  
 다음과 같은 경우에만 형식이 다른 두 포인터를 비교할 수 있습니다.  
  
-   한 형식이 다른 형식에서 파생 클래스 형식입니다.  
  
-   하나 이상의 포인터가 void \* 형식으로 명시적으로 변환됩니다.  다른 포인터는 변환을 위해 void \* 형식으로 암시적으로 변환됩니다.  
  
 형식이 같은 두 포인터가 같은 개체를 가리킬 경우 동일하다고 간주합니다.  개체의 비정적 멤버에 대한 두 포인터를 비교할 경우 다음 규칙이 적용됩니다.  
  
-   클래스 형식이 공용 구조체가 아닐 경우 그리고 공용, 보호 또는 전용 등의 *access\-specifier*로 두 멤버가 구분되지 않은 경우 마지막에 선언된 멤버의 포인터가 먼저 선언된 멤버의 포인터보다 크다고 간주합니다.  *access\-specifier*에 대한 자세한 내용은 [액세스 지정자](../misc/access-specifiers.md)의 구문 섹션을 참조하세요.  
  
-   두 멤버가 *access\-specifier*로 구분되면 결과가 정의되지 않습니다.  
  
-   클래스 형식이 공용 구조체일 경우 해당 공용 구조체의 여러 데이터 멤버에 대한 포인터가 같다고 간주합니다.  
  
 포인터 2개가 배열이 같은 요소를 가리키거나 배열의 끝을 벗어난 요소를 가리킬 경우 첨자가 높은 개체의 포인터가 더 높다고 간주합니다.  포인터가 같은 배열의 개체를 참조하거나 배열의 끝을 벗어난 위치를 참조할 경우에만 포인터 비교가 유효합니다.  
  
## 참고 항목  
 [이항 연산자로 구성된 식](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 관계 및 같음 연산자](../c-language/c-relational-and-equality-operators.md)