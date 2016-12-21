---
title: "컴파일러 오류 C2514 | Microsoft Docs"
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
  - "C2514"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2514"
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2514
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 클래스에 생성자가 없습니다.  
  
 클래스, 구조체 또는 공용 구조체에 이를 인스턴스화하는 데 사용되는 매개 변수에 대응하는 매개 변수 목록을 사용하는 생성자가 없습니다.  
  
 클래스를 인스턴스화하려면 먼저 완전히 선언해야 합니다.  
  
 다음 샘플에서는 C2514 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```