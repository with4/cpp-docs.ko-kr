---
title: "호출 예제: 함수 프로토타입 및 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "호출 규칙, 예제[C++]"
  - "예제[C++], 호출 규칙"
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 호출 예제: 함수 프로토타입 및 호출
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 다음 예제에서는 다양한 호출 규칙을 사용하여 함수를 호출한 결과를 보여 줍니다.  
  
 이 예제는 다음과 같은 함수 구조를 기반으로 합니다.  `calltype`을 적절한 호출 규칙으로 바꾸십시오.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 자세한 내용은 [호출 예제 결과](../cpp/results-of-calling-example.md)를 참조하십시오.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [호출 규칙](../cpp/calling-conventions.md)