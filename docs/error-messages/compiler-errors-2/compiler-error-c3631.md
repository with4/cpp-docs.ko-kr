---
title: "컴파일러 오류 C3631 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3631"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3631"
ms.assetid: 88cbd2d5-6fef-4940-be34-d8cbe816d3da
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3631
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 관리되는 이벤트 또는 WinRT 이벤트를 오버로드할 수 없습니다.  
  
 관리되는 이벤트 또는 WinRT 이벤트를 오버로드할 수 없습니다.  
  
## 예제  
 C3631 오류는 **\/clr:oldSyntax**를 사용해서만 도달할 수 있습니다.  
  
 다음 샘플에서는 C3631 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3631.cpp  
// compile with: /clr:oldSyntax /c  
  
public __gc struct S2 {  
   __event void func1();     
   __event void func1(int);   // C3631 delete second declaration of func1  
};  
  
public __gc struct S1 {  
   __delegate void del1();  
   __delegate void del2();  
   __event int add_myE(del1*) { return 0; }     
   __event int remove_myE(del1*) { return 0; }     
   __event int add_myE(del2*) { return 0; }   // C3631  
   __event int remove_myE(del2*) { return 0; }   // C3631  
};  
```