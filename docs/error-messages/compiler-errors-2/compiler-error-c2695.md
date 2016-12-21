---
title: "컴파일러 오류 C2695 | Microsoft Docs"
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
  - "C2695"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2695"
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2695
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function1' : 재정의 가상 함수는 'function2'과\(와\) 호출 규칙만 다릅니다.  
  
 파생 클래스의 함수 시그니처는 기본 클래스의 함수를 재정의할 수 없으며 호출 규칙을 변경할 수도 없습니다.  
  
 다음 샘플에서는 C2695 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2695.cpp  
class C {  
   virtual void __fastcall func();  
};  
  
class D : public C {  
   virtual void __clrcall func();   // C2695  
};  
```