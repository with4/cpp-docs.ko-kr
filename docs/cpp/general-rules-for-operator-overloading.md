---
title: "연산자 오버 로드에 대 한 일반 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operator overloading [C++], rules
ms.assetid: eb2b3754-35f7-4832-b1da-c502893dc0c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 199db318eb847687d10044e0376b70c8d6d44feb
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="general-rules-for-operator-overloading"></a>연산자 오버로드에 대한 일반 규칙
다음 규칙은 오버로드된 연산자를 구현하는 방법을 제한합니다. 그러나에 적용 되지 않습니다는 [새](../cpp/new-operator-cpp.md) 및 [삭제](../cpp/delete-operator-cpp.md) 은 별도로 다루는 연산자.  
  
-   **와 같은 새 연산자를 정의할 수 없습니다.  
  
-   기본 제공 데이터 형식에 적용할 때 연산자의 의미를 다시 정의할 수 없습니다.  
  
-   오버로드된 연산자는 비정적 클래스 멤버 함수 또는 전역 함수여야 합니다. private 또는 protected 클래스 멤버에 액세스해야 하는 전역 함수는 해당 클래스의 friend로 선언해야 합니다. 전역 함수는 클래스 또는 열거형 형식이거나 클래스 또는 열거형 형식에 대한 참조인 인수를 하나 이상 사용해야 합니다. 예를 들어:  
  
    ```  
    // rules_for_operator_overloading.cpp  
    class Point  
    {  
    public:  
        Point operator<( Point & );  // Declare a member operator   
                                     //  overload.  
        // Declare addition operators.  
        friend Point operator+( Point&, int );  
        friend Point operator+( int, Point& );  
    };  
  
    int main()  
    {  
    }  
    ```  
  
     위의 코드 예제에서는 작음 연산자를 멤버 함수로 선언합니다. 그러나 더하기 연산자는 friend 액세스 권한이 있는 전역 함수로 선언됩니다. 지정된 연산자에 대해 둘 이상의 구현이 제공될 수 있습니다. 위에 나오는 더하기 연산자의 경우 원활한 가환성을 위해 두 가지 구현이 제공됩니다. `Point`를 `Point`에 추가하고 `int`를 `Point`에 추가하는 등의 기능을 하는 연산자가 구현될 수도 있습니다.  
  
-   연산자는 기본 제공 형식과 함께 연산자를 사용하는 일반적인 경우에 적용되는 피연산자의 수, 우선 순위 및 그룹화를 준수합니다. 따라서 개념을 표현할 수 없는 방법이 있습니다. "형식의 개체에 2와 3 추가 `Point`," 2에 추가할 필요는 *x* 좌표와 3에 추가할 수는 *y* 조정 합니다.  
  
-   멤버 함수로 선언된 단항 연산자는 인수를 사용하지 않습니다. 전역 함수로 선언된 경우 인수를 한 개 사용합니다.  
  
-   멤버 함수로 선언된 이항 연산자는 인수를 한 개 사용합니다. 전역 함수로 선언된 경우 인수를 두 개 사용합니다.  
  
-   단항 또는 이항 연산자는 연산자를 사용할 수 있으면 (**&**, **\***, **+**, 및 **-**)를 별도로 각각 사용을 오버 로드할 수 있습니다.  
  
-   오버로드된 연산자는 기본 인수를 사용할 수 없습니다.  
  
-   할당(`operator=`)을 제외한 모든 오버로드된 연산자는 파생 클래스에서 상속합니다.  
  
-   멤버 함수 오버로드된 연산자의 첫 번째 인수는 항상 연산자가 호출되는 개체의 클래스 형식입니다(연산자가 선언된 클래스 또는 해당 클래스에서 파생된 클래스). 첫 번째 인수에 대한 변환은 제공되지 않습니다.  
  
 모든 연산자의 의미는 완전히 변경될 수 있습니다. 주소의 의미를 포함 하는 (**&**), 할당 (**=**), 및 함수 호출 연산자. 또한 기본 제공 형식에 의존할 수 있는 ID는 연산자 오버로드를 사용하여 변경할 수 있습니다. 예를 들어 다음 네 개의 문은 완전히 평가되면 일반적으로 동일합니다.  
  
```  
var = var + 1;  
var += 1;  
var++;  
++var;  
```  
  
 연산자를 오버로드하는 클래스 형식의 경우 이 ID에 의존할 수 없습니다. 또한 기본 형식에 대한 이러한 연산자의 사용에서 암시적인 일부 요구 사항은 오버로드된 연산자의 경우 완화됩니다. 예를 들어 `+=`라는 더하기/할당 연산자를 사용하려면 기본 형식에 적용된 경우 왼쪽 피연산자가 l-value가 되어야 합니다. 연산자가 오버로드되는 경우에는 이러한 요구 사항이 없습니다.  
  
> [!NOTE]
>  일관성을 위해 오버로드된 연산자를 정의하는 경우 기본 제공 형식의 모델을 따르는 것이 가장 좋습니다. 오버로드된 연산자의 의미 체계가 다른 컨텍스트에서의 해당 의미와 크게 다른 경우 유용하기보다 혼동을 줄 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 오버로드](../cpp/operator-overloading.md)