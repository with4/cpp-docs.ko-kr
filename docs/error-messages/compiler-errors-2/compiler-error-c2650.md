---
title: "컴파일러 오류 C2650 | Microsoft Docs"
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
  - "C2650"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2650"
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2650
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 가상 함수일 수 없습니다.  
  
 `new` 또는 `delete` 연산자가 `virtual`로 선언되었습니다.  이러한 연산자는 `static` 멤버 함수이며 `virtual`이 될 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C2650 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```