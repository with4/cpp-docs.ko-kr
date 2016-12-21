---
title: "논리 부정 연산자: ! | Microsoft Docs"
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
  - "!"
  - "Not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! operator"
  - "논리 부정"
  - "NOT 연산자"
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 논리 부정 연산자: !
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
! cast-expression  
```  
  
## 설명  
 논리 부정 연산자\(**\!**\)는 해당 피연산자의 의미를 반대로 바꿉니다.  피연산자는 산술 형식, 포인터 형식 또는 산술\/포인터 형식으로 계산되는 식이어야 합니다.  피연산자는 암시적으로 `bool` 형식으로 변환됩니다.  변환된 피연산자가 **false**이면 결과는 **true**이고 변환된 피연산자가 **true**이면 결과는 **false**입니다.  결과는 `bool` 형식입니다.  
  
 *e* 식의 경우 단항 식 **\!***e*는 오버로드된 연산자가 포함되는 부분을 제외하고 **\(***e* `==` 0\) 식과 동일합니다.  
  
## \!에 대한 연산자 키워드  
 **not** 연산자는 **\!**를 텍스트로 표현한 것입니다.  프로그램에서는 헤더 파일 `iso646.h`를 포함하거나 [\/Za](../build/reference/za-ze-disable-language-extensions.md)\(언어 확장 사용 안 함\) 컴파일러 옵션으로 컴파일하는 두 가지 방법으로 **not** 연산자에 액세스할 수 있습니다.  
  
## 예제  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## 참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [단항 산술 연산자](../c-language/unary-arithmetic-operators.md)