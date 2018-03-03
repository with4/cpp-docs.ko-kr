---
title: "논리 OR 연산자: | | | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '||'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a826b23f94c4eae4a4fdb5379563b015f05dde71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="logical-or-operator-"></a>논리합 연산자: ||
## <a name="syntax"></a>구문  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## <a name="remarks"></a>설명  
 논리 OR 연산자 (`||`) 부울 값을 반환 **true** 경우 피연산자 중 하나 또는 둘 다 **true** 반환 **false** 그렇지 않은 경우. 피연산자는 계산 전에 `bool` 형식으로 암시적 변환되므로 연산 결과가 `bool` 형식이 됩니다. 논리 OR은 왼쪽에서 오른쪽으로의 결합성을 가집니다.  
  
 논리 OR 연산자의 피연산자는 동일한 형식일 필요는 없지만 정수 계열 또는 포인터 형식이어야 합니다. 피연산자는 일반적으로 관계형 또는 동등 식입니다.  
  
 첫 번째 피연산자가 완전히 계산되고 모든 파생 작업이 완료된 후에 논리 OR 계산이 시작됩니다.  
  
 두 번째 피연산자는 첫 번째 피연산자가 false(0)인 경우에만 계산됩니다. 이는 논리 OR 식이 true일 때 두 번째 피연산자를 불필요하게 계산하지 않게 합니다.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 위의 예제에서 `x`가 `w`, `y` 또는 `z`와 같을 경우 `printf` 함수에 대한 두 번째 인수는 true로 계산되고 값 1이 출력됩니다. 그렇지 않으면 false로 계산되고 값 0이 출력됩니다. 조건 중 하나가 true로 확인되면 계산이 중지됩니다.  
  
## <a name="operator-keyword-for-124124"></a>에 대 한 연산자 키워드 &#124; &#124;  
 **또는** 연산자는 해당 하는 텍스트 `||`합니다. 두 가지 방법으로 액세스 하는 **또는** 를 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션입니다.  
  
## <a name="example"></a>예  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
[C + + 기본 제공 연산자 우선순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md) [c + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 논리 연산자](../c-language/c-logical-operators.md)