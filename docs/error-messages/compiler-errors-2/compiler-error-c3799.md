---
title: "컴파일러 오류 C3799 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3799"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3799"
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3799
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인덱싱된 속성은 빈 매개 변수 목록을 가질 수 없습니다.  
  
 인덱싱된 속성을 잘못 선언했습니다.  자세한 내용은 [방법: 인덱싱된 속성 사용](../../misc/how-to-use-indexed-properties.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3799 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3799.cpp  
// compile with: /clr /c  
ref struct C {  
   property int default[] {   // C3799  
   // try the following line instead  
   // property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
```