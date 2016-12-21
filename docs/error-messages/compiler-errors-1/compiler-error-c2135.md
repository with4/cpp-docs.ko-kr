---
title: "컴파일러 오류 C2135 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2135"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2135"
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2135
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'비트 연산자': 비트 필드 연산이 잘못되었습니다.  
  
 address\-of 연산자\(`&`\)는 비트 필드에 적용할 수 없습니다.  
  
 다음 샘플에서는 C2135를 생성합니다.  
  
```  
// C2135.cpp struct S { int i : 1; }; struct T { int j; }; int main() { &S::i;   // C2135 address of a bit field &T::j;   // OK }  
```