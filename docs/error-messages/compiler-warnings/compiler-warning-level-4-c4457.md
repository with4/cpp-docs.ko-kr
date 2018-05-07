---
title: 컴파일러 경고 (수준 4) C4457 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80eac0ade54df1626e993bfed12468b2aa34402f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4457"></a>컴파일러 경고 (수준 4) C4457
  
> 선언 '*식별자*' 숨깁니다 함수 매개 변수
  
선언 *식별자* 로컬 범위에서 동일 하 게 명명 된 함수 매개 변수 선언을 숨깁니다. 이 경고를 사용 하면에 대 한 참조를 알 *식별자* 로컬 범위에서 해결 로컬로 선언 된 버전으로 매개 변수가 아닌 되거나 의도 되지 않을 수 있습니다. 이 문제를 해결 하려면 매개 변수 이름과 충돌 하지 않는 지역 변수 이름을 지정 해야 하는 것이 좋습니다.  
    
## <a name="example"></a>예제
  
때문에 다음 샘플에서는 C4457 매개 변수 `x` 및 지역 변수 `x` 에 `member_fn` 이름이 같습니다. 이 문제를 해결 하려면 다른 이름을 매개 변수 및 지역 변수를 사용 합니다.  
  
```cpp  
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        } 
        a += x; // uses parameter x
    }
} s;
```  
