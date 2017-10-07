---
title: "비트 포함 OR 연산자: | | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitor
- '|'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: bb2fcc7c85e112b80929b2a8392f0e6c19ab97f2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bitwise-inclusive-or-operator-"></a>포괄적 비트 OR 연산자: |
## <a name="syntax"></a>구문  
  
```  
  
expression   
|  
 expression  
  
```  
  
## <a name="remarks"></a>설명  
 비트 포함 OR 연산자 (**&#124;**) 두 번째 피연산자의 해당 비트의 첫 번째 피연산자의 각 비트와 비교 합니다. 어느 한쪽 비트가 1이면 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.  
  
 포괄적 비트 OR 연산자에 대한 두 피연산자는 모두 정수 계열 형식이어야 합니다. 다루는 일반적인 산술 변환은 [표준 변환](standard-conversions.md) 피연산자에 적용 됩니다.  
  
## <a name="operator-keyword-for-124"></a>에 대 한 연산자 키워드 &#124;  
 `bitor` 연산자는 해당 하는 텍스트 **&#124;**합니다. 두 가지 방법으로 액세스 하는 `bitor` 를 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션입니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 비트 연산자](../c-language/c-bitwise-operators.md)


