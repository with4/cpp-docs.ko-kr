---
title: "컴파일러 경고 (수준 4) C4457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
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
ms.openlocfilehash: 4977ade625e3f4af5f01364b865d2c2f41ebe80a
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

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

