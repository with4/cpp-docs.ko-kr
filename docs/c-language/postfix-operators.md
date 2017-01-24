---
title: "후위 연산자 | Microsoft Docs"
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
  - "연산자[C], 후위"
  - "후위 연산자"
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 후위 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

후위 연산자는 식 계산에서 가장 높은 우선 순위\(가장 강력한 바인딩\)를 가집니다.  
  
## 구문  
 후위 식:  
 *primary\-expression*  
  
 *postfix\-expression*  **\[**  *expression*  **\]**  
  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *postfix\-expression*  **.**  *identifier*  
  
 *postfix\-expression*  **–\>**  *identifier*  
  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 이 우선 순위 수준에 있는 연산자는 배열 첨자, 함수 호출, 구조체 및 공용 구조체 멤버 및 후위 증가\/감소 연산자입니다.  
  
## 참고 항목  
 [C 연산자](../c-language/c-operators.md)