---
title: "컴파일러 오류 C2524 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2524"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2524"
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2524
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'destructor' : 소멸자\/종료자에는 'void' 매개 변수 목록이 있어야 합니다.  
  
 소멸자나 종료자에 [void](../../cpp/void-cpp.md)가 아닌 매개 변수 목록이 있습니다.  다른 매개 변수 형식은 사용할 수 없습니다.  
  
## 예제  
 다음 코드를 실행하면 C2524가 발생합니다.  
  
```  
// C2524.cpp  
// compile with: /c  
class A {  
   A() {}  
   ~A(int i) {}    // C2524  
   // try the following line instead  
   // ~A() {}  
};  
```  
  
## 예제  
 다음 코드를 실행하면 C2524가 발생합니다.  
  
```  
// C2524_b.cpp  
// compile with: /clr /c  
ref struct I1 {  
protected:  
   !I1(int i);   // C2524  
   // try the following line instead  
   // !I1();  
};  
```