---
title: "논리곱 연산자: &amp;&amp; | Microsoft Docs"
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
  - "&&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "&amp;&amp; 연산자"
  - "AND 연산자"
  - "논리곱 연산자"
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 논리곱 연산자: &amp;&amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## 설명  
 논리 AND 연산자\(**&&**\)는 두 피연산자가 모두 **true**이면 부울 값 **true**를 반환하고, 그렇지 않으면 **false**를 반환합니다.  피연산자는 계산 전에 `bool` 형식으로 암시적 변환되므로 연산 결과가 `bool` 형식이 됩니다.  논리 AND에는 왼쪽에서 오른쪽으로의 결합성이 있습니다.  
  
 논리 AND 연산자의 피연산자는 동일한 형식일 필요는 없지만 정수 계열 또는 포인터 형식이어야 합니다.  피연산자는 일반적으로 관계형 또는 동등 식입니다.  
  
 첫째 피연산자가 완전히 계산되고 의도하지 않은 모든 결과가 논리 AND 식의 계산을 계속하기 전에 완료됩니다.  
  
 둘째 피연산자는 첫째 피연산자가 true\(0이 아님\)인 경우에만 계산됩니다.  이 계산으로 인해 논리 AND 식이 false일 때 둘째 피연산자의 불필요한 계산이 배제됩니다.  다음 예제와 같이 이 단락\(short\-circuit\) 계산을 사용하여 null 포인터 역참조를 방지할 수 있습니다.  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 `pch`가 null\(0\)인 경우 식의 오른쪽이 계산되지 않습니다.  따라서 null 포인터를 통해 할당할 수 없습니다.  
  
## &&에 대한 연산자 키워드  
 **and** 연산자는 **&&**를 텍스트로 표현한 것입니다.  프로그램에서는 헤더 파일 `iso646.h`를 포함하거나 [\/Za](../build/reference/za-ze-disable-language-extensions.md)\(언어 확장 사용 안 함\) 컴파일러 옵션으로 컴파일하는 두 가지 방법으로 **and** 연산자에 액세스할 수 있습니다.  
  
## 예제  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## 참고 항목  
 [논리 연산자](../misc/logical-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 논리 연산자](../c-language/c-logical-operators.md)