---
title: "전처리기 문법 | Microsoft Docs"
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
  - "문법, 전처리기"
  - "전처리기"
  - "전처리기, 문법"
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 전처리기 문법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#define**  *identifier* *token\-string*opt  
  
 *\#* **define**  *identifier*\[**\(** *identifier*opt**,** *...* **,** *identifier*opt **\)**\] *token\-string*opt  
  
 **defined\(**  *identifier* **\)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path\-spec***"**  
  
 `#include` **\<***path\-spec***\>**  
  
 **\#line**  *digit\-sequence*  **"** *filename* **"** opt  
  
 *\#* **undef**  *identifier*  
  
 **\#error**  *token\-string*  
  
 **\#pragma**  *token\-string*  
  
 *conditional* :  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part* :  
 *if\-linetext*  
  
 *if\-line* :  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts* :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line* :  
 **\#elif**  *constant\-expression*  
  
 *else\-part* :  
 *else\-linetext*  
  
 *else\-line* :  
 `#else`  
  
 *endif\-line* :  
 `#endif`  
  
 *digit\-sequence* :  
 *digit*  
  
 *digit\-sequence digit*  
  
 *digit* : 다음 중 하나  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *token\-string* :  
 토큰 문자열  
  
 *token* :  
 *keyword*  
  
 *식별자*  
  
 *상수*  
  
 *연산자*  
  
 `punctuator`  
  
 *filename* :  
 올바른 운영 체제 파일 이름  
  
 *path\-spec* :  
 Legal file path  
  
 *text* :  
 임의의 텍스트 시퀀스  
  
> [!NOTE]
>  다음 비터미널은 *C\+\+ 언어 참조*의 부록 A인 [문법 요약](../misc/grammar-summary-cpp.md)에 더 자세히 설명되어 있습니다\(`constant`, `constant`\-*expression*, *identifier*, *keyword*, `operator` 및 `punctuator`\).  
  
## 참고 항목  
 [문법 요약](../preprocessor/grammar-summary-c-cpp.md)