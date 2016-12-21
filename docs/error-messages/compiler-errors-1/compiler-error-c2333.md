---
title: "컴파일러 오류 C2333 | Microsoft Docs"
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
  - "C2333"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2333"
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2333
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수 선언에 오류가 있습니다. 함수 본문을 건너뜁니다.  
  
 이 오류는 해당 클래스 내부에 정의된 멤버 함수에 대해 다른 오류가 발생한 후에 발생합니다.  
  
 다음 샘플에서는 C2333 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2333.cpp  
struct s1 {  
   s1(s1) {}   // C2333  
};  
```