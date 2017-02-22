---
title: "컴파일러 오류 C2130 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2130"
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#line에 파일 이름을 포함하는 문자열이 있어야 하는데 'token'이 있습니다.  
  
 [\#line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` 뒤에 오는 선택적 파일 이름 토큰은 문자열이어야 합니다.  
  
 다음 샘플에서는 C2130을 생성합니다.  
  
```  
// C2130.cpp int main() { #line 1000 test   // C2130 #line 1000 "test"   // OK }  
```