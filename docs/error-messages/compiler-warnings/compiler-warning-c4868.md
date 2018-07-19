---
title: 컴파일러 경고 C4868 | Microsoft Docs
ms.date: 10/26/2017
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 922a1a8434da8449758b9d55ebe89ace2f262cd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275244"
---
# <a name="compiler-warning-level-4-c4868"></a>컴파일러 경고 (수준 4) C4868

> '_파일_(*line_number*)' 컴파일러는 중괄호로 묶인된 이니셜라이저 목록에서 왼쪽에서 오른쪽 평가 순서를 적용할 수 없습니다.

중괄호로 묶인된 이니셜라이저 목록의 요소가 왼쪽에서 오른쪽 순서로 계산 되도록 합니다. 두 가지 경우에는 컴파일러에서이 순서를 보장할 수 없는: 첫 번째 요소 중 일부는 값으로 전달 된 개체는 로 컴파일하는 경우 두 번째는 `/clr` 및는 개체의 필드 또는 배열 요소는 요소 중 일부입니다. 컴파일러 왼쪽-오른쪽으로 계산 하지 못할 경우 경고를 C4868 내보냅니다.

Visual c + + 2015 업데이트 2에 대해 수행한 컴파일러 규칙 작업의 결과로이 경고를 생성할 수 있습니다. 이제 Visual c + + 2015 업데이트 2 이전에 컴파일된 코드 C4868를 생성할 수 있습니다.

기본적으로 이 경고는 해제되어 있습니다. 사용 하 여 `/Wall` 이 경고를 활성화 합니다.

이 경고를 해결 하려면 먼저 이니셜라이저 목록 요소의 왼쪽-오른쪽으로 계산 요소 평가 순서 대로 부작용을 생성할 수 있습니다 때와 같이 필요한 인지 고려 합니다. 대부분의 경우에서 요소 평가 되는 순서 없는 눈에 띄는 효과가 있습니다.

계산 순서는 왼쪽에서 오른쪽 수 있어야 할 경우 고려 하 여 요소를 전달할 수는 `const` 대신 참조 해야 합니다. 이 변경 된 다음 코드 예제에서이 경고를 제거합니다.

## <a name="example"></a>예제

이 샘플에서는 C4868, 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```