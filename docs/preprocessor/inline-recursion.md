---
title: "inline_recursion | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inline_recursion_CPP"
  - "vc-pragma.inline_recursion"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "inline_recursion pragma"
  - "pragma, inline_recursion"
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# inline_recursion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

직접 또는 상호 재귀 함수 호출의 인라인 확장을 제어합니다.  
  
## 구문  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## 설명  
 [inline](../misc/inline-inline-forceinline.md) 및 [\_\_inline](../misc/inline-inline-forceinline.md)으로 표시된 함수나 컴파일러가 \/Ob2 옵션에서 자동으로 확장하는 함수를 제어하려면 이 pragma를 사용합니다.  이 pragma를 사용하려면 [\/Ob](../build/reference/ob-inline-function-expansion.md) 컴파일러 옵션을 1 또는 2로 설정해야 합니다.  `inline_recursion`의 기본 상태는 off입니다.  이 pragma는 pragma가 표시된 후 첫 번째 함수에서 적용되며 함수의 정의에는 영향을 미치지 않습니다.  
  
 `inline_recursion` pragma는 재귀 함수가 확장되는 방식을 제어합니다.  `inline_recursion`이 off인 경우 인라인 함수가 자신을 호출하면\(직접적 또는 간접적으로\) 함수는 한 번만 확장됩니다.  `inline_recursion`이 on인 경우 함수가 [inline\_depth](../preprocessor/inline-depth.md) pragma로 설정된 값, `inline_depth` pragma로 정의된 재귀 함수의 기본값 또는 용량 한도에 도달할 때까지 여러 번 확장됩니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_depth](../preprocessor/inline-depth.md)   
 [\/Ob\(인라인 함수 확장\)](../build/reference/ob-inline-function-expansion.md)