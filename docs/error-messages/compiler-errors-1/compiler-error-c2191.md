---
title: "컴파일러 오류 C2191 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2191"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2191"
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2191
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

둘째 매개 변수 목록이 첫째보다 깁니다.  
  
 C 함수가 긴 매개 변수 목록을 사용하여 두 번 선언되었습니다.  C는 오버로드된 함수를 지원하지 않습니다.  
  
## 예제  
 다음 샘플에서는 C2191 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```