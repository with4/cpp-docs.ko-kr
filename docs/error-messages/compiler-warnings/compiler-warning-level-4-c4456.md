---
title: "컴파일러 경고 (수준 4) C4456 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
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
ms.openlocfilehash: 8698c9a430a79bbec1f6e82b8ac58067317c59a1
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4456"></a>컴파일러 경고 (수준 4) C4456
  
> 선언 '*식별자*' 이전 로컬 선언을 숨깁니다.
  
선언 *식별자* 로컬 범위에서 같은 이름의 이전 로컬 선언의 선언을 숨깁니다. 이 경고를 사용 하면에 대 한 참조를 알 *식별자* 로컬 범위에서 로컬로 선언 된 버전을 의도 하지 못할 수도 있습니다는 이전 로컬 하지으로 확인 합니다. 이 문제를 해결 하려면 다른 로컬 이름과 충돌 하지 않는 지역 변수 이름을 지정 해야 하는 것이 좋습니다.  
    
## <a name="example"></a>예제
  
루프 제어 변수 하기 때문에 다음 샘플에서는 C4456 `int x` 및 지역 변수 `double x` 에 `member_fn` 이름이 같습니다. 이 문제를 해결 하려면 지역 변수에 대 한 서로 다른 이름을 사용 합니다.  
  
```cpp  
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        } 
        x += u; // uses local double x
    }
} s;
```  

