---
title: "컴파일러 오류 C2849 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2849"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2849"
ms.assetid: e28f6b3e-e0e7-4f92-b006-ebaa81d368e6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2849
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'destructor' : 인터페이스에 소멸자를 사용할 수 없습니다.  
  
 Visual C\+\+ [interface](../../cpp/interface.md)에 소멸자를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2849 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2849.cpp  
// compile with: /c  
__interface C {  
   ~C();   // C2849 destructor not allowed in an interface  
};  
```