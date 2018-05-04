---
title: 곱하기 연산자 및 나머지 연산자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '%'
- /
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], multiplicative
- arithmetic operators [C++], multiplicative operators
- modulus operator [C++]
- '* operator'
- division operator [C++], multiplicative operators
- '% operator'
- multiplication operator [C++], multiplicative operators
- multiplicative operators [C++]
- division operator
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 129dce32dfe0ba50a07b71d2fcfaf72bdade090e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="multiplicative-operators-and-the-modulus-operator"></a>곱하기 연산자 및 나머지 연산자
## <a name="syntax"></a>구문  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## <a name="remarks"></a>설명  
 곱하기 연산자는 다음과 같습니다.  
  
-   곱하기 (**\****)  
  
-   나누기 (**/**)  
  
-   모듈러스(나누기의 나머지)(`%`)  
  
 이 이항 연산자는 왼쪽에서 오른쪽으로 연결됩니다.  
  
 곱하기 연산자는 산술 형식의 피연산자를 사용합니다. 모듈러스 연산자(`%`)에는 피연산자가 정수 계열 형식이어야 한다는 엄격한 요구 사항이 적용됩니다. (부동 소수점 나누기의 나머지를 가져올를 런타임에 함수를 사용 하려면 [fmod](../c-runtime-library/reference/fmod-fmodf.md).) 설명한 변환이 [표준 변환](standard-conversions.md) 피연산자에 적용 되 고 결과 변환 된 형식입니다.  
  
 곱하기 연산자는 첫 번째 피연산자와 두 번째 피연산자를 곱한 결과를 구합니다.  
  
 나누기 연산자는 첫 번째 피연산자를 두 번째 피연산자로 나눈 결과를 구합니다.  
  
 모듈러스 연산자는 다음 식에서 제공한 나머지를 구합니다. 여기서 *e1* 첫 번째 피연산자는 및 *e2* 은 두 번째: *e1* -(*e1*  /  *e2*) \* *e2*에서 두 피연산자가 정수 계열 형식입니다.  
  
 0으로 나누기는 나누기 또는 모듈러스 식에 정의되지 않았으며 런타임 오류를 생성합니다. 따라서 다음 식에서는 정의되지 않은 잘못된 결과가 생성됩니다.  
  
```  
i % 0  
f / 0.0  
```  
  
 곱하기, 나누기 또는 모듈러스 식의 두 피연산자 모두 부호가 같고 결과는 양수입니다. 그렇지 않으면 결과는 음수입니다. 모듈러스 연산 부호의 결과는 구현에서 정의됩니다.  
  
> [!NOTE]
>  곱셈 연산자로 수행된 변환은 오버플로 또는 언더플로 조건을 제공하지 않으므로 변환 후 곱셈 연산 결과가 피연산자 형식으로 표현되지 않는 경우 정보가 손실될 수 있습니다.  
  
## <a name="microsoft-specific"></a>Microsoft 전용  
 Microsoft C++에서 모듈러스 식의 결과가 항상 첫 번째 피연산자의 부호와 같습니다.  
  
**Microsoft 전용 종료**  
 두 정수의 나누기 계산이 정확하지 않고 피연산자가 한 개만 음수일 경우 나누기 연산에서 구하는 정확한 값보다 작은 최대 정수(부호에 관계 없는 크기)가 결과가 됩니다. 예를 들어-11의 계산된 값 3은-3.666666666 / 합니다. 이 정수 나누기의 결과는-3입니다.  
  
 곱셈 연산자 간의 관계를 지정 하 여 id (*e1* / *e2*) \* *e2*  +  *e1* % *e2* == *e1*합니다.  
  
## <a name="example"></a>예제  
 다음 프로그램은 곱셈 연산자를 보여 줍니다. 피연산자 중 하나가 `10 / 3` 입력으로 명시적으로 캐스팅 되어야 합니다 `float` 잘림을 방지 하 여 두 피연산자가를 `float` 나누기 앞입니다.  
  
```  
// expre_Multiplicative_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   int x = 3, y = 6, z = 10;  
   cout  << "3 * 6 is " << x * y << endl  
         << "6 / 3 is " << y / x << endl  
         << "10 % 3 is " << z % x << endl  
         << "10 / 3 is " << (float) z / x << endl;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)   
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 곱하기 연산자](../c-language/c-multiplicative-operators.md)