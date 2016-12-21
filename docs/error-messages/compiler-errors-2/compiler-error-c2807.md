---
title: "컴파일러 오류 C2807 | Microsoft Docs"
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
  - "C2807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2807"
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

후위 'operator operator'의 둘째 형식 매개 변수는 'int'이어야 합니다.  
  
 후위 연산자에 대한 둘째 매개 변수의 형식이 잘못되었습니다.  
  
 다음 샘플에서는 C2807 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2807.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( X );   // C2807 nonvoid parameter  
   X operator++ ( int );   // OK, int parameter  
};  
```