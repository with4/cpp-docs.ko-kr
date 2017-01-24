---
title: "포괄적 비트 OR 연산자: | | Microsoft Docs"
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
  - "bitor"
  - "|"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "| 연산자"
  - "비트 연산자, Or 연산자"
  - "포함 OR 연산자"
  - "Or 연산자, 비트 포함"
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 포괄적 비트 OR 연산자: |
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
expression   
|  
 expression  
  
```  
  
## 설명  
 포괄적 비트 OR 연산자\(         **&#124;** \)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다.  어느 한쪽 비트가 1이면 해당 결과 비트는 1로 설정됩니다.  그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.  
  
 포괄적 비트 OR 연산자에 대한 두 피연산자는 모두 정수 계열 형식이어야 합니다.  [산술 변환](../misc/arithmetic-conversions.md)에서 다루는 일반적인 산술 변환은 피연산자에 적용됩니다.  
  
## &#124;에 대한 연산자 키워드  
 `bitor` 연산자는 다음의 텍스트에 해당하는 것입니다.              **&#124;** .  프로그램에서 `bitor` 연산자에 액세스하는 두 가지 방법이 있습니다. 헤더 파일 `iso646.h`를 포함하거나 [\/Za](../build/reference/za-ze-disable-language-extensions.md)\(언어 확장 사용 안 함\) 컴파일러 옵션으로 컴파일하는 것입니다.  
  
## 예제  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## 참고 항목  
 [C\+\+ 비트 연산자](../misc/cpp-bitwise-operators.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 비트 연산자](../c-language/c-bitwise-operators.md)