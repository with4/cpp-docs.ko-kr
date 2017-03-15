---
title: "inline_depth | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inline_depth_CPP"
  - "vc-pragma.inline_depth"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inline_depth pragma"
  - "pragma, inline_depth"
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# inline_depth
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수가 호출 그래프에서 `n`보다 큰 수준으로 인라인 처리되지 않도록 인라인 추론 검색 수준을 지정합니다.  
  
## 구문  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## 설명  
 이 pragma는 [inline](../misc/inline-inline-forceinline.md) 및 [\_\_inline](../misc/inline-inline-forceinline.md)으로 표시되거나 \/Ob2 옵션에서 자동적으로 인라인 처리된 함수의 인라이닝을 제어합니다.  
  
 `n`은 0에서 255 사이의 값입니다. 여기서 255는 호출 그래프의 수준이 무제한임을 의미하고 0은 인라인 확장을 금지함을 의미합니다.  `n`이 지정되지 않은 경우 기본값\(254\)이 사용됩니다.  
  
 **Inline\_depth** pragma는 일련의 함수 호출을 확장할 수 있는 횟수를 제어합니다.  예를 들어, 인라인 깊이가 4개이고 A가 B를 호출한 후 B가 C를 호출할 경우 3개의 호출이 모두 인라인 확장됩니다.  그러나 최대 인라인 확장이 2개일 경우 A와 B만 확장되고 C는 함수 호출로 남게 됩니다.  
  
 이 pragma를 사용하려면 \/Ob 컴파일러 옵션을 1 또는 2로 설정해야 합니다.  이 pragma를 사용하여 설정한 깊이는 pragma 뒤에 오는 첫 번째 함수 호출에 적용됩니다.  
  
 인라인 깊이는 확장하는 동안 감소할 수 있지만 증가하지 않습니다.  인라인 깊이가 6이고 확장 중에 전처리기에서 값이 8인 **inline\_depth** pragma가 발생할 경우 깊이는 6으로 유지됩니다.  
  
 **inline\_depth** pragma는 `__forceinline`이 표시된 함수에는 영향을 주지 않습니다.  
  
> [!NOTE]
>  재귀 함수는 최대 16 깊이의 호출까지 인라인을 대체할 수 있습니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_recursion](../preprocessor/inline-recursion.md)