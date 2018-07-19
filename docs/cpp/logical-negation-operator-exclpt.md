---
title: '논리 부정 연산자: ! | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6c8ad17195954feeeccb47896fa013302b6d7e3
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944485"
---
# <a name="logical-negation-operator-"></a>논리 부정 연산자: !
## <a name="syntax"></a>구문  
  
```  
  
! cast-expression  
```  
  
## <a name="remarks"></a>설명  
 논리 부정 연산자 (**!**)는 피연산자의 의미를 반대로 바꿉니다. 피연산자는 산술 형식, 포인터 형식 또는 산술/포인터 형식으로 계산되는 식이어야 합니다. 피연산자 형식으로 암시적으로 변환 됩니다 **bool**합니다. 결과 TRUE이 고 변환 된 피연산자가 FALSE; 결과 변환 된 피연산자가 TRUE 이면 FALSE입니다. 결과 형식의 **bool**합니다.  
  
 식에 대 한 *e*, 단항 식 **! * * * e* 식에 해당 하는 **(* * * e* `==` 0)를 오버 로드 된 연산자와 관련 된를 제외 하 고 합니다.  
  
## <a name="operator-keyword-for-"></a>!에 대한 연산자 키워드  
 합니다 **되지** 연산자는 해당 하는 텍스트 **!** 합니다. 두 가지 방법으로 액세스 하는 **하지** 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션.  
  
## <a name="example"></a>예  
  
```cpp 
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [단항 산술 연산자](../c-language/unary-arithmetic-operators.md)