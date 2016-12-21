---
title: "배타적 비트 OR 연산자: ^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "^ 연산자"
  - "비트 연산자, Or 연산자"
  - "배타적 OR 연산자"
  - "연산자[C++], 비트"
  - "연산자[C++], 논리적"
  - "Or 연산자, 배타적 비트"
  - "XOR 연산자"
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 배타적 비트 OR 연산자: ^
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
expression ^ expression  
```  
  
## 설명  
 배타적 비트 OR 연산자\(**^**\)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다.  한 비트가 0이고 다른 비트가 1인 경우 해당 결과 비트는 1로 설정됩니다.  그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.  
  
 배타적 비트 OR 연산자에 대한 피연산자는 둘 다 정수 계열 형식이어야 합니다.  [산술 변환](../misc/arithmetic-conversions.md)에서 다루는 일반적인 산술 변환은 피연산자에 적용됩니다.  
  
## ^에 대한 연산자 키워드  
 **xor** 연산자는 **^**에 해당하는 텍스트입니다.  프로그램에서 `iso646.h` 헤더 파일을 포함하거나 [\/Za](../build/reference/za-ze-disable-language-extensions.md)\(언어 확장 사용 안 함\) 컴파일러 옵션으로 컴파일하는 두 가지 방법으로 **xor** 연산자에 액세스할 수 있습니다.  
  
## 예제  
  
```  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## 참고 항목  
 [C\+\+ 비트 연산자](../misc/cpp-bitwise-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 비트 연산자](../c-language/c-bitwise-operators.md)