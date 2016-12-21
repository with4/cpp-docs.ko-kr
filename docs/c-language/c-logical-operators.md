---
title: "C 논리 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "&amp;&amp; 연산자"
  - "|| 연산자"
  - "논리곱 연산자"
  - "논리 연산자, C"
  - "논리 연산자, 식 시퀀스 위치"
  - "논리합 연산자"
  - "연산자[C], 논리적"
  - "단락(short-circuit) 연산"
ms.assetid: c0a4e766-ad56-4300-bf76-b28dc0e19b43
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 논리 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

논리 연산자는 논리 AND\(**&&**\) 및 논리 OR\(`||` \) 작업을 수행합니다.  
  
 **구문**  
  
 *logical\-AND\-expression*:  
 *inclusive\-OR\-expression*  
  
 *logical\-AND\-expression*  **&&**  *inclusive\-OR\-expression*  
  
 *logical\-OR\-expression*:  
 *logical\-AND\-expression*  
  
 *logical\-OR\-expression*  **&#124;&#124;**  *logical\-AND\-expression*  
  
 논리 연산자는 일반적인 산술 변환을 수행하지 않습니다.  대신, 0에 해당하는 개념으로 각 피연산자를 평가합니다.  논리 연산의 결과는 0 또는 1입니다.  결과는 `int` 형식입니다.  
  
 C 논리 연산자는 다음과 같습니다.  
  
|연산자|설명|  
|---------|--------|  
|**&&**|논리 AND 연산자는 두 피연산자가 모두 0이 아닌 값이 있는 경우 값 1을 생성합니다.  피연산자 중 하나가 0이면 결과는 0입니다.  논리 AND 연산의 첫째 피연산자가 0인 경우, 두 번째 피연산자는 계산되지 않습니다.|  
|`&#124;&#124;`|논리\-OR 연산자는 피연산자에서 포괄 OR 연산을 수행합니다.  두 피연산자가 모두 0 값이 있는 경우 결과는 0입니다.  피연산자 중 하나에 0이 아닌 값이 있는 경우 결과는 1입니다.  논리 OR 연산의 첫째 피연산자에 0이 아닌 값이 있는 경우, 둘째 피연산자는 계산되지 않습니다.|  
  
 논리 AND 및 논리 OR 식의 피연산자는 왼쪽에서 오른쪽으로 평가됩니다.  첫째 피연산자의 값이 연산 결과를 확인하는 데 충분할 경우 둘째 피연산자는 계산되지 않습니다.  이것을 "단락\(short\-circuit\) 계산"이라고 합니다. 첫 번째 피연산자 다음에 시퀀스 위치가 있습니다.  자세한 내용은 [시퀀스 위치](../c-language/c-sequence-points.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 논리 연산자를 보여 줍니다.  
  
```  
int w, x, y, z;  
  
if ( x < y && y < z )  
    printf( "x is less than z\n" );  
```  
  
 이 예제에서는 `x`가 `y`보다 작고 `y`가 `z`보다 작은 경우 `printf` 함수가 호출되고 메시지를 인쇄합니다.  `x`가 `y`보다 크면 두 번째 피연산자\(`y < z`\)가 계산되지 않고 아무것도 출력되지 않습니다.  이는 두 번째 피연산자에 다른 이유로 의존되는 파생 효과가 있는 경우에 문제를 일으킬 수 있습니다.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 이 예제에서 `x`가 `w`, `y` 또는 `z`와 같을 경우 `printf` 함수에 대한 두 번째 인수는 true로 계산되고 값 1이 인쇄됩니다.  그렇지 않으면 false로 계산되고 값 0이 출력됩니다.  조건 중 하나가 true로 확인되면 계산이 중지됩니다.  
  
## 참고 항목  
 [논리곱 연산자: &&](../cpp/logical-and-operator-amp-amp.md)   
 [논리합 연산자: &#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)