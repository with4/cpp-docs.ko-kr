---
title: "컴파일러 오류 C3755 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3755"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3755"
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3755
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delegate': 대리자를 정의할 수 없습니다.  
  
 [delegate](../../windows/delegate-cpp-component-extensions.md)는 선언할 수 있지만 정의할 수는 없습니다.  
  
## 예제  
 다음 샘플에서는 C3755 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3755.cpp  
// compile with: /clr /c  
delegate void MyDel() {};   // C3755  
```  
  
## 예제  
 대리자 템플릿을 만드는 경우에도 C3755가 발생할 수 있습니다.  다음 샘플에서는 C3755 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3755_b.cpp  
// compile with: /clr /c  
ref struct R {  
   template<class T>  
   delegate void D(int) {}   // C3755  
};  
```