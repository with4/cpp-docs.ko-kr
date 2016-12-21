---
title: "컴파일러 오류 C2575 | Microsoft Docs"
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
  - "C2575"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2575"
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2575
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 멤버 함수와 기본만 virtual일 수 있습니다.  
  
 전역 함수 또는 클래스가 `virtual`로 선언되었습니다.  이것은 허용되지 않습니다.  
  
 다음 샘플에서는 C2575 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2575.cpp  
// compile with: /c  
virtual void func() {}   // C2575  
  
void func2() {}  
struct A {  
   virtual void func2(){}  
};  
```