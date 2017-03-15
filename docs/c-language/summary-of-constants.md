---
title: "상수 요약 | Microsoft Docs"
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
  - "상수, C"
ms.assetid: 4158234c-e189-4e25-970f-52a04bc6380a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 상수 요약
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`constant`:  
 *floating\-point\-constant*  
  
 *integer\-constant*  
  
 *enumeration\-constant*  
  
 *character\-constant*  
  
 *floating\-point\-constant*:  
 *fractional\-constant exponent\-part*  opt *floating\-suffix* opt  
  
 *digit\-sequence exponent\-part floating\-suffix*  opt  
  
 *fractional\-constant*:  
 *digit\-sequence*  opt **.***digit\-sequence*  
  
 *digit\-sequence*  **.**  
  
 *exponent\-part*:  
 **e**  *sign*  opt *digit\-sequence*  
  
 **E**  *sign*  opt *digit\-sequence*  
  
 *sign*: 다음 중 하나  
 **\+ –**  
  
 *digit\-sequence*:  
 *digit*  
  
 *digit\-sequence digit*  
  
 *floating\-suffix*: 다음 중 하나  
 **f l F L**  
  
 *integer\-constant*:  
 *decimal\-constant integer\-suffix*  opt  
  
 *octal\-constant integer\-suffix*  opt  
  
 *hexadecimal\-constant integer\-suffix*  opt  
  
 *decimal\-constant*:  
 *nonzero\-digit*  
  
 *decimal\-constant digit*  
  
 *octal\-constant*:  
 **0**  
  
 *octal\-constant octal\-digit*  
  
 *hexadecimal\-constant*:  
 **0x**  *hexadecimal\-digit*  
  
 **0X**  *hexadecimal\-digit*  
  
 *hexadecimal\-constant hexadecimal\-digit*  
  
 *nonzero\-digit*: 다음 중 하나  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal\-digit*: 다음 중 하나  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal\-digit*: 다음 중 하나  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *unsigned\-suffix*: 다음 중 하나  
 **u U**  
  
 *long\-suffix*: 다음 중 하나  
 **l L**  
  
 문자 상수:  
 **'** *c\-char\-sequence*  
  
 **'L'** *c\-char\-sequence* **'**  
  
 *integer\-suffix*:  
 *unsigned\-suffix long\-suffix*  opt  
  
 *long\-suffix unsigned\-suffix*  opt  
  
 *c\-char* 시퀀스:  
 *c\-char*  
  
 *c\-char\-sequence c\-char*  
  
 *c\-char*:  
 작은따옴표\('\), 백슬래시\(**\\**\) 또는 줄 바꿈 문자 *escape\-sequence*를 제외한 소스 문자 집합의 모든 멤버  
  
 *escape\-sequence*이스케이프 시퀀스:  
 *단순 이스케이프 시퀀스*  
  
 *8진수 이스케이프 시퀀스*  
  
 *16진수 이스케이프 시퀀스*  
  
 단순 이스케이프 시퀀스: 다음 중 하나  
 **\\a \\b \\f \\n \\r \\t \\v**  
  
 **\\' \\" \\\\ \\?**  
  
 8진수 이스케이프 시퀀스:  
 **\\** *octal\-digit*  
  
 **\\** *octal\-digit octal\-digit*  
  
 **\\** *octal\-digit octal\-digit octal\-digit*  
  
 16진수 이스케이프 시퀀스:  
 **\\x**  *hexadecimal\-digit*  
  
 *hexadecimal\-escape\-sequence hexadecimal\-digit*  
  
## 참고 항목  
 [어휘 문법](../c-language/lexical-grammar.md)