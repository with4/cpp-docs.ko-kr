---
title: "컴파일러 오류 C2798 | Microsoft Docs"
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
  - "C2798"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2798"
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2798
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super::member'이\(가\) 모호합니다.  
  
 [super](../../cpp/super.md)를 사용하여 참조하는 멤버가 여러 개의 상속된 구조체에 포함됩니다.  다음 중 하나를 수행하면 이 오류를 해결할 수 있습니다.  
  
-   D의 상속 목록에서 B1 또는 B2를 제거합니다.  
  
-   B1 또는 B2의 데이터 멤버 이름을 변경합니다.  
  
 다음 샘플에서는 C2798 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```