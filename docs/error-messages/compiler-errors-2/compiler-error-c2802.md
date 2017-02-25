---
title: "컴파일러 오류 C2802 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2802"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2802"
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2802
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정적 멤버 'operator operator'에 형식 매개 변수가 없습니다.  
  
 `static` 멤버 함수가 선언한 연산자에는 매개 변수가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C2802 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2802.cpp  
// compile with: /clr /c  
ref class A {  
   static operator+ ();   // C2802  
   static operator+ (A^, A^);   // OK  
};  
```