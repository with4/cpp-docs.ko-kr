---
title: "비트 AND 연산자: &amp; | Microsoft Docs"
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
  - "bitand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 연산자, 비트 연산자"
  - "AND 연산자"
  - "비트 연산자, AND 연산자"
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 비트 AND 연산자: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
expression   
&  
 expression  
  
```  
  
## 설명  
 식은 다른 and 식이거나 아래에서 설명한 형식 제한에 따라 같음 식, 관계식, 더하기 식, 곱하기 식, 멤버 포인터 식, 캐스트 식, 단항 식, 후위 식 또는 기본 식일 수 있습니다.  
  
 비트 AND 연산자\(**&**\)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다.  양쪽 비트가 모두 1이면 해당 결과 비트는 1로 설정됩니다.  그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.  
  
 비트 AND 연산자에 대한 두 피연산자는 모두 정수 계열 형식이어야 합니다.  [산술 변환](../misc/arithmetic-conversions.md)에서 다루는 일반적인 산술 변환은 피연산자에 적용됩니다.  
  
## &에 대한 연산자 키워드  
 `bitand` 연산자는 **&**에 해당하는 텍스트입니다.  프로그램에서 `bitand` 연산자에 액세스하는 두 가지 방법이 있습니다. 헤더 파일 `iso646.h`를 포함하거나 [\/Za](../build/reference/za-ze-disable-language-extensions.md)\(언어 확장 사용 안 함\) 컴파일러 옵션으로 컴파일하는 것입니다.  
  
## 예제  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## 참고 항목  
 [C\+\+ 비트 연산자](../misc/cpp-bitwise-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 비트 연산자](../c-language/c-bitwise-operators.md)