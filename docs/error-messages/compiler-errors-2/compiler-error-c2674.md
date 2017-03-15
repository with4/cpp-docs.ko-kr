---
title: "컴파일러 오류 C2674 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2674"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2674"
ms.assetid: 7cbd70d8-d992-44d7-a5cb-dd8cf9c759d2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2674
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 컨텍스트에서는 제네릭 선언이 허용되지 않습니다.  
  
 제네릭이 잘못 선언되었습니다.  자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2674 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2674.cpp  
// compile with: /clr /c  
void F(generic <class T> ref class R1);   // C2674  
generic <class T> ref class R2 {};   // OK  
```