---
title: "함수와 매크로 중 선택에 대한 권장 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.functions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수[CRT], 매크로와 비교"
  - "매크로, 함수와 비교"
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 함수와 매크로 중 선택에 대한 권장 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대부분의 Microsoft 런타임 라이브러리 루틴은 컴파일되거나 조립 된 함수입니다. 그러나 일부 루틴은 매크로로 구현 됩니다.  헤더 파일은 함수와 루틴의 매크로 버전 모두를 선언 할 때 항상 함수 선언 후 나타나기 때문에, 매크로 정의가 우선시됩니다.  매크로와 함수로 구현 된 루틴을 호출할 때 두 가지 방법으로 함수 버전을 사용 하여 강제로 컴파일할 수있습니다.  
  
-   루틴 이름을 괄호로 묶어야 합니다.  
  
    ```  
    #include <ctype.h>  
    a = _toupper(a);    // Use macro version of toupper.  
    a = (_toupper)(a);  // Force compiler to use   
                        // function version of toupper.  
    ```  
  
-   `#undef` 지시문을 사용한 "Undefine" 매크로 정의 :  
  
    ```  
    #include <ctype.h>  
    #undef _toupper  
    ```  
  
 함수 및 라이브러리 루틴을 구현하는 매크로 중 하나를 선택 해야 할 경우 다음 사항을 고려해 야 합니다.  
  
-   **Speed versus size** 이 매크로의 주요 장점은 실행 시간을 단축시키는 것입니다.  전처리 하는 동안 매크로는 \(정의 의해 교체\) 인라인이 사용 될 때마다 확장 됩니다.  함수 정의는 호출 횟수에 관계 없이 한 번만 발생 합니다.  매크로 코드 크기가 증가할 수 있습니다 그러나 함수 호출과 관련된 오버 헤드가 필요는 없습니다.  
  
-   **Function evaluation** 함수는 매크로는 하지 않는 주소를 계산합니다.  따라서 포인터를 요구하는 컨텍스트에서 매크로 이름을 사용할 수 없습니다.  예를 들어, 함수에 대한 포인터를 선언할 수 있지만, 매크로에 대한 함수는 선언할 수 없습니다.  
  
-   **Type\-checking** 함수를 선언 할 때 컴파일러는 인수 형식을 검사할 수 있습니다.  비록 매크로로 전달 된 인수의 수는 검사할 수 있어도 매크로를 선언할 수 없기 때문에, 컴파일러는 매크로 인수 형식을 검사할 수 없습니다.  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)