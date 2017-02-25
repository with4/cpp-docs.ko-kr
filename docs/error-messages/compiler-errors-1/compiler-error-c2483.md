---
title: "컴파일러 오류 C2483 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2483"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2483"
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2483
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 생성자 또는 소멸자가 있는 개체는 'thread'로 선언할 수 없습니다.  
  
 `thread` 특성을 통해 선언된 변수는 런타임 계산에 필요한 생성자나 다른 식에서 초기화할 수 없습니다.  `thread` 데이터 초기화에는 정적 식이 필요합니다.  
  
## 예제  
 다음 샘플에서는 C2483 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2483.cpp  
// compile with: /c  
__declspec(thread) struct A {  
   A(){}  
   ~A(){}  
} aa;   // C2483 error  
  
__declspec(thread) struct B {} b;   // OK  
```  
  
## 참고 항목  
 [스레드](../../cpp/thread.md)