---
title: "컴파일러 오류 C3766 | Microsoft Docs"
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
  - "C3766"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3766"
ms.assetid: b5af2089-2e1e-4e45-a41d-495b6c55656e
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3766
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type'은\(는\) 인터페이스 메서드 'function'에 대한 구현을 제공해야 합니다.  
  
 인터페이스에서 상속되는 클래스는 인터페이스 멤버를 구현해야 합니다.  
  
## 예제  
 다음 샘플에서는 C3766 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3766.cpp  
// compile with: /clr /c  
  
delegate void MyDel();  
  
interface struct IFace {  
   virtual event MyDel ^ E;  
};  
  
ref struct Class1 : public IFace {};   // C3766  
  
// OK  
ref struct Class2 : public IFace {  
   virtual event MyDel ^ E {  
      void add(MyDel ^) {}  
      void remove(MyDel ^) {}  
   }  
};  
```