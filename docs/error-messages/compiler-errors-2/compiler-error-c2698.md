---
title: "컴파일러 오류 C2698 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2698"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2698"
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2698
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration 1'의 using 선언은 'declaration 2'의 기존 using 선언과 함께 사용할 수 없습니다.  
  
 데이터 멤버에 대해 [using 선언](../../cpp/using-declaration.md)을 사용하면 함수만 오버로드할 수 있으므로 동일 범위에서 동일 이름을 사용하는 using 선언을 사용할 수 없습니다.  
  
 다음 샘플에서는 C2698 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```