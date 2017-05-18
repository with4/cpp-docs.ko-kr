---
title: "컴파일러 경고 (수준 4) C4458 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
caps.latest.revision: 0
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 07b8db673b2db27f456f0e7228695c83497d1278
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4458"></a>컴파일러 경고 (수준 4) C4458
  
> 선언 '*식별자*' 클래스 멤버를 숨깁니다
  
선언 *식별자* 로컬 범위에서 같은 이름의 선언을 숨깁니다 *식별자* 클래스 범위에 있습니다. 이 경고를 사용 하면에 대 한 참조를 알 *식별자* 이 범위에 로컬로 선언 된 버전, 클래스 멤버 버전이 아니라, 의도 하지 못할 수도 있습니다는으로 확인 합니다. 이 문제를 해결 하려면 클래스 멤버 이름과 충돌 하지 않는 지역 변수 이름을 지정 해야 하는 것이 좋습니다.  
    
## <a name="example"></a>예제
  
때문에 다음 샘플에서는 C4458 매개 변수 `x` 및 지역 변수 `y` 에 `member_fn` 클래스의 데이터 멤버와 동일한 이름이 있습니다. 이 문제를 해결 하려면 다른 이름을 매개 변수 및 지역 변수를 사용 합니다.  
  
```cpp  
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;  
        // To fix this issue, change the parameter name x
        // and local name y to something that does not 
        // conflict with the data member names.
    }
} s;
```  

