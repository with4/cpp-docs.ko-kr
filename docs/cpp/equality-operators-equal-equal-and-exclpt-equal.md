---
title: "같음 연산자: = = 및! = | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- not_eq
- '!='
- ==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5412869204f088e321d2a41da407026f9447eb82
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="equality-operators--and-"></a>같음 연산자: == 및 !=
## <a name="syntax"></a>구문  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>설명  
 이항 같음 연산자는 피연산자를 비교하여 완전히 같은지 아니면 같지 않은지를 확인합니다.  
  
 같음 연산자에는 같음(`==`)과 같지 않음(`!=`)이 있으며 이러한 연산자는 관계형 연산자보다 우선 순위가 낮지만 비슷하게 동작합니다. 이러한 연산자의 결과 형식은 `bool`입니다.  
  
 같음 연산자 (`==`) 반환 **true** (1) 동일한 값을 포함 하는 두 피연산자 모두; 그렇지 않으면 반환 **false** (0). Not 같음 연산자 (`!=`) 반환 **true** 피연산자; 같은 값을 사용 하지 않은 경우 그렇지 **false**합니다.  
  
## <a name="operator-keyword-for-"></a>!=에 대한 연산자 키워드  
 `not_eq` 연산자는 `!=`에 해당하는 텍스트입니다. 두 가지 방법으로 액세스 하는 `not_eq` 를 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션입니다.  
  
## <a name="example"></a>예제  
  
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
  
 같음 연산자는 동일한 형식의 멤버에 대한 포인터를 비교할 수 있습니다. 이러한 비교에서는 멤버 포인터 변환 수행 됩니다. 멤버에 대한 포인터를 0으로 계산되는 상수 식과 비교할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)   
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 관계 및 같음 연산자](../c-language/c-relational-and-equality-operators.md)
