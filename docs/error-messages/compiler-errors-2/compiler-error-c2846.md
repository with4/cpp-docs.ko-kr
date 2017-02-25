---
title: "컴파일러 오류 C2846 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2846"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2846"
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2846
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constructor' : 인터페이스에 생성자를 사용할 수 없습니다.  
  
 Visual C\+\+ [interface](../../cpp/interface.md)에 생성자를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2846 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2846.cpp  
// compile with: /c  
__interface C {  
   C();   // C2846 constructor not allowed in an interface  
};  
```