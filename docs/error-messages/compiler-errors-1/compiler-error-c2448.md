---
title: "컴파일러 오류 C2448 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2448"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2448"
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2448
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 함수 스타일 이니셜라이저가 함수 정의처럼 나타납니다.  
  
 함수 정의가 잘못되었습니다.  
  
 이 오류는 이전 스타일의 C 언어 형식 목록을 사용하는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2448 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```