---
title: "컴파일러 경고 (수준 1) C4584 | Microsoft Docs"
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
  - "C4584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4584"
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class1' : 'class2' 기본 클래스가 이미 'class3'의 기본 클래스입니다.  
  
 정의한 클래스가 서로 상속 관계에 있는 두 개의 클래스에서 상속되었습니다.  예를 들면 다음과 같습니다.  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 이 경우 C 클래스는 A 클래스와 A 클래스에서 상속되는 B 클래스에서 동시에 상속되었으므로 C 클래스에서 경고가 발생합니다.  이 경고는 이러한 기본 클래스의 멤버를 사용할 수 없다는 것을 나타내며 참조한 클래스 멤버가 모호하므로 컴파일러 오류가 발생합니다.