---
title: "곱하기 연산자 및 나머지 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "%"
  - "/"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "% 연산자"
  - "* 연산자"
  - "산술 연산자[C++], 곱하기 연산자"
  - "나누기 연산자"
  - "나누기 연산자, 곱하기 연산자"
  - "나머지 연산자, C+"
  - "곱하기 연산자[C++], 곱하기 연산자"
  - "승제 연산자[C++]"
  - "연산자[C++], 승제"
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 곱하기 연산자 및 나머지 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## 설명  
 곱하기 연산자는 다음과 같습니다.  
  
-   곱하기\(**\***\)  
  
-   나누기\(**\/**\)  
  
-   모듈러스\(나누기의 나머지\)\(`%`\)  
  
 이 이항 연산자는 왼쪽에서 오른쪽으로 연결됩니다.  
  
 곱하기 연산자는 산술 형식의 피연산자를 사용합니다.  모듈러스 연산자\(`%`\)에는 피연산자가 정수 계열 형식이어야 한다는 엄격한 요구 사항이 적용됩니다. 부동 소수점 나누기의 나머지를 구하려면 런타임 함수 [fmod](../c-runtime-library/reference/fmod-fmodf.md)를 사용하십시오. [산술 변환](../misc/arithmetic-conversions.md)에서 설명하는 변환은 피연산자에 적용되며 결과는 변환된 형식입니다.  
  
 곱하기 연산자는 첫 번째 피연산자와 두 번째 피연산자를 곱한 결과를 구합니다.  
  
 나누기 연산자는 첫 번째 피연산자를 두 번째 피연산자로 나눈 결과를 구합니다.  
  
 모듈러스 연산자는 다음 식에서 제공한 나머지를 구합니다. *e1*은 첫 번째 피연산자이고 *e2*는 두 번째 피연산자입니다. *e1* – \(*e1* \/ *e2*\) \* *e2*에서 두 피연산자가 모두 정수 계열 형식입니다.  
  
 0으로 나누기는 나누기 또는 모듈러스 식에 정의되지 않았으며 런타임 오류를 생성합니다.  따라서 다음 식에서는 정의되지 않은 잘못된 결과가 생성됩니다.  
  
```  
i % 0  
f / 0.0  
```  
  
 곱하기, 나누기 또는 모듈러스 식의 두 피연산자 모두 부호가 같고 결과는 양수입니다.  그렇지 않으면 결과는 음수입니다.  모듈러스 연산 부호의 결과는 구현에서 정의됩니다.  
  
> [!NOTE]
>  곱셈 연산자로 수행된 변환은 오버플로 또는 언더플로 조건을 제공하지 않으므로 변환 후 곱셈 연산 결과가 피연산자 형식으로 표현되지 않는 경우 정보가 손실될 수 있습니다.  
  
## Microsoft 전용  
 Microsoft C\+\+에서 모듈러스 식의 결과가 항상 첫 번째 피연산자의 부호와 같습니다.  
  
## Microsoft 전용 종료  
 두 정수의 나누기 계산이 정확하지 않고 피연산자가 한 개만 음수일 경우 나누기 연산에서 구하는 정확한 값보다 작은 최대 정수\(부호에 관계 없는 크기\)가 결과가 됩니다.  예를 들어, –11 \/ 3의 계산된 값은 –3.666666666입니다.  이 정수 나누기의 결과는 –3입니다.  
  
 ID\(*e1* \/ *e2*\) \* *e2* \+ *e1* % *e2* \=\= *e1*로 곱셈 연산자 간의 관계가 지정됩니다.  
  
## 예제  
 다음 프로그램은 곱셈 연산자를 보여 줍니다.  `10 / 3`의 피연산자가 정확히 `float` 형식으로 캐스팅되어야 잘림을 방지하여 두 피연산자 모두 나누기 앞에서 `float` 형식이 됩니다.  
  
```  
// expre_Multiplicative_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   int x = 3, y = 6, z = 10;  
   cout  << "3 * 6 is " << x * y << endl  
         << "6 / 3 is " << y / x << endl  
         << "10 % 3 is " << z % x << endl  
         << "10 / 3 is " << (float) z / x << endl;  
}  
```  
  
## 참고 항목  
 [이항 연산자로 구성된 식](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [곱하기 연산자](../c-language/c-multiplicative-operators.md)