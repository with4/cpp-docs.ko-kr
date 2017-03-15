---
title: "컴파일러 오류 C2624 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2624"
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지역 클래스를 'extern' 변수를 선언하는 데 사용할 수 없습니다.  
  
 지역 클래스 또는 구조체는 `extern` 변수를 선언하는 데 사용할 수 없습니다.  
  
 다음 샘플에서는 C2624 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```