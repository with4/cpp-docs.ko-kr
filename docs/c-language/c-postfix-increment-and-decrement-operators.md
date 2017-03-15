---
title: "C 후위 증가 및 감소 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "증가 연산자, 구문"
  - "스칼라 연산자"
  - "형식[C], 스칼라"
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C 후위 증가 및 감소 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

후위 증가 및 감소 연산자의 피연산자는 수정 가능한 l\-value인 스칼라 형식입니다.  
  
## 구문  
 후위 식:  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 후위 증가 또는 감소 연산의 결과는 피연산자의 값입니다.  결과를 얻은 후에는 피연산자의 값이 증가 또는 감소합니다.  다음 코드에서는 후위 증가 연산자를 보여 줍니다.  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 이 예제에서 `var` 변수는 0과 비교된 다음 증가됩니다.  `var`이 증가되기 전에 양수였던 경우 다음 문이 실행됩니다.  먼저 `q`가 가리키는 개체의 값이 `p`가 가리키는 개체에 할당됩니다.  그런 다음 `q` 및 `p`가 증가됩니다.  
  
## 참고 항목  
 [후위 증가 및 감소 연산자: \+\+ 및 \-\-](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)