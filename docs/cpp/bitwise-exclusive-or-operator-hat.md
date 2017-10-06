---
title: "배타적 비트 OR 연산자: ^ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c6d7713a28fa6c0dbe7a5543afa65cd927f614e7
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bitwise-exclusive-or-operator-"></a>배타적 비트 OR 연산자: ^
## <a name="syntax"></a>구문  
  
```  
expression ^ expression  
```  
  
## <a name="remarks"></a>설명  
배타적 비트 OR 연산자 (**^**) 두 번째 피연산자의 해당 비트의 첫 번째 피연산자의 각 비트와 비교 합니다. 한 비트가 0이고 다른 비트가 1인 경우 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.  
  
배타적 비트 OR 연산자에 대한 피연산자는 둘 다 정수 계열 형식이어야 합니다. 다루는 일반적인 산술 변환은 [표준 변환](standard-conversions.md) 피연산자에 적용 됩니다.  
  
## <a name="operator-keyword-for-"></a>^에 대한 연산자 키워드  
**xor** 연산자는 해당 하는 텍스트 ** ^ **합니다. 두 가지 방법으로 액세스 하는 **xor** 를 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션입니다.  
  
## <a name="example"></a>예제  
  
```cpp  
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
  
## <a name="see-also"></a>참고 항목  
 [C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   



