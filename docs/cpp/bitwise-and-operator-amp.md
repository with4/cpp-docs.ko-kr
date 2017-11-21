---
title: "비트 논리곱 연산자: &amp; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: bitand
dev_langs: C++
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2bf6369e0404705d84533778357f7fe339c7ef55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="bitwise-and-operator-amp"></a>비트 논리곱 연산자:&amp;
## <a name="syntax"></a>구문  
  
```  
  
expression   
&  
 expression  
  
```  
  
## <a name="remarks"></a>설명  
 식은 다른 and 식이거나 아래에서 설명한 형식 제한에 따라 같음 식, 관계식, 더하기 식, 곱하기 식, 멤버 포인터 식, 캐스트 식, 단항 식, 후위 식 또는 기본 식일 수 있습니다.  
  
 비트 AND 연산자 (**&**) 두 번째 피연산자의 해당 비트를 첫 번째 피연산자의 각 비트와 비교 합니다. 양쪽 비트가 모두 1이면 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.  
  
 비트 AND 연산자에 대한 두 피연산자는 모두 정수 계열 형식이어야 합니다. 다루는 일반적인 산술 변환은 [표준 변환](standard-conversions.md)을 피연산자에 적용 됩니다.  
  
## <a name="operator-keyword-for-"></a>에 대 한 연산자 키워드 &  
 `bitand` 연산자는 해당 하는 텍스트  **&** 합니다. 두 가지 방법으로 액세스 하는 `bitand` 를 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션입니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C++ 기본 제공 연산자, 우선 순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md)  
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 비트 연산자](../c-language/c-bitwise-operators.md)