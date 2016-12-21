---
title: "컴파일러 오류 C2794 | Microsoft Docs"
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
  - "C2794"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2794"
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2794
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 직접 또는 간접 기본 클래스 'class'의 멤버가 아닙니다.  
  
 [super](../../cpp/super.md)를 사용하여 존재하지 않는 멤버 함수를 호출하려고 했습니다.  
  
 다음 샘플에서는 C2794 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```