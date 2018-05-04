---
title: '하나의&#39;s 보수 연산자: ~ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- "~"
dev_langs:
- C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a10c8f3df2a1f2f27ee33450a52132e8184d4232
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="one39s-complement-operator-"></a>하나의&#39;s 보수 연산자: ~
## <a name="syntax"></a>구문  
  
```  
  
~ cast-expression  
```  
  
## <a name="remarks"></a>설명  
 "비트 보수" 연산자라고도 하는 1의 보수 연산자(`~`)는 해당 피연산자의 비트 1의 보수를 생성합니다. 즉, 피연산자의 1인 모든 비트는 결과적으로 0입니다. 반대로 피연산자의 0인 모든 비트는 결과적으로 1입니다. 1의 보수 연산자의 피연산자는 정수 계열 형식이어야 합니다.  
  
## <a name="operator-keyword-for-"></a>~에 대한 연산자 키워드  
 `compl` 연산자는 `~`에 해당하는 텍스트입니다. 두 가지 방법으로 액세스 하는 `compl` 를 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`, 사용 하 여 컴파일 또는 [/Za](../build/reference/za-ze-disable-language-extensions.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 이 예제에서 `y`에 할당된 새 값은 부호 없는 값인 0xFFFF의 1의 보수이거나 0x0000입니다.  
  
 정수 계열 확장은 정수 계열 피연산자에서 수행되며, 결과 형식은 피연산자가 확장되는 형식입니다. 참조 [표준 변환](standard-conversions.md) 확장 수행 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [단항 산술 연산자](../c-language/unary-arithmetic-operators.md)