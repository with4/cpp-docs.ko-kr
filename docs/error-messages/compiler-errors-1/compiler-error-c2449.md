---
title: "컴파일러 오류 C2449 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2449"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2449"
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2449
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 범위에 '{'가 있습니다. 함수 헤더가 없는 것 같습니다.  
  
 파일 범위에 여는 중괄호가 있습니다.  
  
 이 오류는 함수 헤더와 함수 정의의 여는 중괄호 사이에 세미콜론이 있는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2499 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```