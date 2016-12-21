---
title: "식 요약 | Microsoft Docs"
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
ms.assetid: ed448953-687a-4b57-a1cb-12967bd770ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 식 요약
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*primary\-expression*:  
 *식별자*  
  
 *상수*  
  
 *문자열 리터럴:*  
  
 **\(**  *expression*  **\)**  
  
 *expression*:  
 *인수 식*  
  
 *expression*  **,**  *assignment\-expression*  
  
 *constant\-expression*:  
 *조건식*  
  
 *conditional\-expression*:  
 *logical\-OR\-expression*  
  
 *logical\-OR\-expression*  **?**  *expression*  **:**  *conditional\-expression*  
  
 할당 식:  
 *조건식*  
  
 *단항 식 할당 연산자 할당 식*  
  
 후위 식:  
 *primary\-expression*  
  
 *postfix\-expression*  **\[**  *expression*  **\]**  
  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *postfix\-expression*  **.**  *identifier*  
  
 *postfix\-expression*  **–\>**  *identifier*  
  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 인수 식 목록:  
 *인수 식*  
  
 인수 식 목록**,** 인수 식  
  
 *unary\-expression*:  
 *postfix\-expression*  
  
 **\+\+**  *unary\-expression*  
  
 **––**  *unary\-expression*  
  
 *unary\-operator*  
  
 *cast\-expression*  
  
 **sizeof**  *unary\-expression*  
  
 **sizeof \(**  *type\-name*  **\)**  
  
 *unary\-operator*: 다음 중 하나  
 **& \* \+ – ~ \!**  
  
 *cast\-expression*:  
 *unary\-expression*  
  
 **\(**  *type\-name*  **\)**  *cast\-expression*  
  
 *multiplicative\-expression*:  
 *cast\-expression*  
  
 *multiplicative\-expression*  **\***  *cast\-expression*  
  
 *multiplicative\-expression*  **\/**  *cast\-expression*  
  
 *multiplicative\-expression*  **%**  *cast\-expression*  
  
 *additive\-expression*:  
 *multiplicative\-expression*  
  
 *additive\-expression*  **\+**  *multiplicative\-expression*  
  
 *additive\-expression*  **–**  *multiplicative\-expression*  
  
 *shift\-expression*:  
 *additive\-expression*  
  
 *shift\-expression*  **\<\<**  *additive\-expression*  
  
 *shift\-expression*  **\>\>**  *additive\-expression*  
  
 *relational\-expression*:  
 *shift\-expression*  
  
 *relational\-expression*  **\<**  *shift\-expression*  
  
 *relational\-expression*  **\>**  *shift\-expression relational\-expression*  **\<\=**  *shift\-expression*  
  
 *relational\-expression*  **\>\=**  *shift\-expression*  
  
 *equality\-expression*:  
 *relational\-expression*  
  
 *equality\-expression*  **\=\=**  *relational\-expression*  
  
 *equality\-expression*  **\!\=**  *relational\-expression*  
  
 *AND\-expression*:  
 *equality\-expression*  
  
 *AND\-expression*  **&**  *equality\-expression*  
  
 *exclusive\-OR\-expression*:  
 *AND\-expression*  
  
 *exclusive\-OR\-expression*  **^**  *AND\-expression*  
  
 *inclusive\-OR\-expression*:  
 *exclusive\-OR\-expression*  
  
 *inclusive\-OR\-expression*  **&#124;**   *exclusive\-OR\-expression*  
  
 *logical\-AND\-expression*:  
 *inclusive\-OR\-expression*  
  
 *logical\-AND\-expression*  **&&**  *inclusive\-OR\-expression*  
  
 *logical\-OR\-expression*:  
 *logical\-AND\-expression*  
  
 *logical\-OR\-expression*  **&#124;&#124;**  *logical\-AND\-expression*  
  
## 참고 항목  
 [구 구조 문법](../c-language/phrase-structure-grammar.md)