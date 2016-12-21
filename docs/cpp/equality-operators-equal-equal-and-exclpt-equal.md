---
title: "같음 연산자: == 및 != | Microsoft Docs"
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
  - "not_eq"
  - "!="
  - "=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= 연산자"
  - "== 연산자"
  - "같음 연산자"
  - "같음 연산자"
  - "같음 연산자, 구문"
  - "같지 않음 비교 연산자"
  - "not_eq 연산자"
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 같음 연산자: == 및 !=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
      expression == expression  
expression != expression  
```  
  
## 설명  
 이항 같음 연산자는 피연산자를 비교하여 완전히 같은지 아니면 같지 않은지를 확인합니다.  
  
 같음 연산자에는 같음\(`==`\)과 같지 않음\(`!=`\)이 있으며 이러한 연산자는 관계형 연산자보다 우선 순위가 낮지만 비슷하게 동작합니다.  이러한 연산자의 결과 형식은 `bool`입니다.  
  
 같음 연산자\(`==`\)는 두 피연산자의 값이 같으면 **true**\(1\)를 반환하고, 그렇지 않으면 **false**\(0\)를 반환합니다.  같지 않음 연산자\(`!=`\)는 두 피연산자의 값이 같지 않으면 **true**를 반환하고, 그렇지 않으면 **false**를 반환합니다.  
  
## \!\=에 대한 연산자 키워드  
 `not_eq` 연산자는 `!=`에 해당하는 텍스트입니다.  프로그램에서 `not_eq` 연산자에 액세스하는 두 가지 방법이 있습니다. 헤더 파일 `iso646.h`를 포함하거나 [\/Za](../build/reference/za-ze-disable-language-extensions.md)\(언어 확장 사용 안 함\) 컴파일러 옵션으로 컴파일하는 것입니다.  
  
## 예제  
  
```  
// expre_Equality_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << boolalpha  
         << "The true expression 3 != 2 yields: "  
         << (3 != 2) << endl  
         << "The false expression 20 == 10 yields: "  
         << (20 == 10) << endl;  
}  
```  
  
 같음 연산자는 동일한 형식의 멤버에 대한 포인터를 비교할 수 있습니다.  이러한 비교에서는 멤버 포인터 변환\([멤버 포인터 변환](../misc/pointer-to-member-conversions.md) 참조\)이 수행됩니다.  멤버에 대한 포인터를 0으로 계산되는 상수 식과 비교할 수도 있습니다.  
  
## 참고 항목  
 [이항 연산자로 구성된 식](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 관계 및 같음 연산자](../c-language/c-relational-and-equality-operators.md)