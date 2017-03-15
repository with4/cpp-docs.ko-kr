---
title: "컴파일러 오류 C2838 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2838"
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2838
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 멤버 선언의 정규화된 이름이 잘못되었습니다.  
  
 클래스, 구조체 또는 공용 구조체가 정규화된 이름을 사용하여 다른 클래스, 구조체 또는 공용 구조체의 멤버를 다시 선언합니다.  
  
 다음 샘플에서는 C2838 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2838.cpp  
// compile with: /c  
class Bellini {  
public:  
    void Norma();  
};  
  
class Bottesini {  
   Bellini::Norma();  // C2838  
};  
```