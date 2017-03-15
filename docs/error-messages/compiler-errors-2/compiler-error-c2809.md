---
title: "컴파일러 오류 C2809 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2809"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2809"
ms.assetid: ce796b8e-1a8c-4074-995d-1ad09afd0e93
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2809
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator'에 형식 매개 변수가 없습니다.  
  
 연산자에 필수 매개 변수가 부족합니다.  
  
 다음 샘플에서는 C2809 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2809.cpp  
// compile with: /c  
class A{};  
int operator+ ();   // C2809  
int operator+ (A);   // OK  
```