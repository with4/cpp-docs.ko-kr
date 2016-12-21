---
title: "컴파일러 오류 C2190 | Microsoft Docs"
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
  - "C2190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2190"
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

첫째 매개 변수 목록이 둘째보다 깁니다.  
  
 C 함수가 짧은 매개 변수 목록을 사용하여 두 번 선언되었습니다.  C는 오버로드된 함수를 지원하지 않습니다.  
  
 다음 샘플에서는 C2190 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2190.c  
// compile with: /Za /c  
void func( int, float );  
void func( int  );   // C2190, different parameter list  
void func2( int  );   // OK  
```