---
title: "컴파일러 경고 C4868 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 26031e1ac6f39d745a772e1becf3f817213a59d8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4868"></a>컴파일러 경고 C4868
'file(line_number)' 컴파일러는 중괄호로 묶인된 이니셜라이저 목록에서 왼쪽에서 오른쪽 평가 순서를 적용 하지 않는다  
  
 중괄호로 묶인된 이니셜라이저 목록 요소가 왼쪽에서 오른쪽 순서로 계산 됩니다. 두 가지 경우에 컴파일러는이 순서를 보장 하기 위해 수 없습니다: 첫 번째 요소 중 일부는 값으로 전달 된 개체는 두 번째는으로 컴파일할 때 `/clr` 는 개체의 필드 또는 배열 요소는 요소 중 일부를 하 고 있습니다. 컴파일러 왼쪽에서 오른쪽 평가 하지 못할 경우 경고를 C4868 내보냅니다.  
  
 이 경고는 Visual c + + 2015 업데이트 2에 대해 수행 된 컴파일러 규칙의 결과로 발생할 수 있습니다. Visual c + + 2015 업데이트 2 이전에 컴파일된 코드를 생성할 C4868 됩니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 사용 하 여 `/Wall` 이 경고를 활성화 합니다.  
  
 이 경고를 해결 하려면 먼저 이니셜라이저 목록 요소의 왼쪽에서 오른쪽 평가 요소는 평가 순서가 부작용을 생성할 수 있습니다 같은 필요 여부를 고려 합니다. 대부분의 경우에서 요소 평가 되는 순서 없는 한 눈에 띄는 효과가 있습니다.  
  
 평가 순서를 왼쪽에서 오른쪽 이어야 하는 경우에 대신 (const) 참조 하 여 요소를 전달할 수는 하는 것이 좋습니다. 이 변경 된 다음 코드 샘플에 대 한 경고를 제거합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4868 오류가 발생 합니다.  
  
```  
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
