---
title: "컴파일러 경고 (수준 4) C4212 | Microsoft Docs"
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
  - "C4212"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4212"
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4212
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 함수 선언에서 줄임표\(...\)를 사용했습니다.  
  
 함수 프로토타입에는 다양한 수의 인수가 있지만  함수 정의에는 인수의 수가 다양하지 않습니다.  
  
 다음 샘플에서는 C4212 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4212.c  
// compile with: /W4 /Ze /c  
void f(int , ...);  
void f(int i, int j) {}  
```