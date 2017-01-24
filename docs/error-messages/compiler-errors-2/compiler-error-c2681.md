---
title: "컴파일러 오류 C2681 | Microsoft Docs"
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
  - "C2681"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2681"
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2681
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 이름에 대한 식 형식이 잘못되었습니다.  
  
 캐스팅 연산자가 잘못된 형식으로부터 변환하려고 했습니다.  예를 들어, [dynamic\_cast](../../cpp/dynamic-cast-operator.md) 연산자를 사용하여 식을 포인터 형식으로 변환하는 경우 소스 식은 포인터여야 합니다.  
  
 다음 샘플에서는 C2681 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```