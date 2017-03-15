---
title: "문 요약 | Microsoft Docs"
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
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 문 요약
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문:  
 *레이블 문*  
  
 *복합 문*  
  
 *식 문*  
  
 *선택 문*  
  
 *반복 문*  
  
 *점프 문*  
  
 *try\-except\-statement* \/\* Microsoft 전용 \*\/  
  
 *try\-finally\-statement* \/\* Microsoft 전용 \*\/  
  
 점프 문:  
 **goto**  *identifier*  **;**  
  
 **continue ;**  
  
 **break ;**  
  
 **return**  *expression* opt **;**  
  
 복합 문:  
 **{**  *declaration\-list* opt *statement\-list* opt **}**  
  
 선언 목록:  
 *선언*  
  
 *선언 목록 선언*  
  
 문 목록:  
 *statement*  
  
 *문 목록 문*  
  
 식 문:  
 *expression* opt **;**  
  
 *iteration\-statement*:  
 **while \(**  *expression*  **\)**  *statement*  
  
 **do**  *statement*  **while \(**  *expression*  **\) ;**  
  
 **for \(**  *expression* opt **;** *expression* opt **;** *expression* opt **\)** *statement*  
  
 *selection\-statement*:  
 **if \(**  *expression*  **\)**  *statement*  
  
 **if \(**  *expression*  **\)**  *statement*  **else**  *statement*  
  
 **switch \(**  *expression*  **\)**  *statement*  
  
 *labeled\-statement*:  
 *identifier*  **:**  *statement*  
  
 **case**  *constant\-expression*  **:**  *statement*  
  
 **default :**  *statement*  
  
 *try\-except\-statement*:   \/\* Microsoft 전용 \*\/  
 **\_\_try**  *compound\-statement*  
  
 **\_\_except \(**  *expression*  **\)**  *compound\-statement*  
  
 *try\-finally\-statement*:   \/\* Microsoft 전용 \*\/  
 **\_\_try**  *compound\-statement*  
  
 **\_\_finally**  *compound\-statement*  
  
## 참고 항목  
 [구 구조 문법](../c-language/phrase-structure-grammar.md)