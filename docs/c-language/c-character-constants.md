---
title: "C 문자 상수 | Microsoft Docs"
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
  - "(') 작은따옴표"
  - "문자, 상수"
  - "상수, 문자"
  - "작은따옴표"
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 문자 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"문자 상수"는 표현 가능한 문자 집합의 단일 문자를 작은따옴표\(**' '**\)로 묶어 구성합니다.  문자 상수는 [실행 문자 집합](../c-language/execution-character-set.md)에서 문자를 나타내는 데 사용됩니다.  
  
## 구문  
 문자 상수:  
 **'** *c\-char\-sequence* **'**  
  
 **'L'** *c\-char\-sequence* **'**  
  
 *c\-char* 시퀀스:  
 *c\-char*  
  
 *c\-char\-sequence c\-char*  
  
 *c\-char*:  
 작은 따옴표\(**'**\), 백슬래시\(**\\**\) 또는 줄 바꿈 문자를 제외한 소스 문자 집합의 모든 멤버  
  
 *이스케이프 시퀀스*  
  
 *escape\-sequence*이스케이프 시퀀스:  
 *단순 이스케이프 시퀀스*  
  
 *8진수 이스케이프 시퀀스*  
  
 *16진수 이스케이프 시퀀스*  
  
 단순 이스케이프 시퀀스: 다음 중 하나  
 **\\a \\b \\f \\n \\r \\t \\v**  
  
 **\\' \\" \\\\ \\?**  
  
 8진수 이스케이프 시퀀스:  
 **\\**  *octal\-digit*  
  
 **\\**  *octal\-digit octal\-digit*  
  
 **\\**  *octal\-digit octal\-digit octal\-digit*  
  
 16진수 이스케이프 시퀀스:  
 **\\x**  *hexadecimal\-digit*  
  
 *hexadecimal\-escape\-sequence hexadecimal\-digit*  
  
## 참고 항목  
 [C 상수](../c-language/c-constants.md)