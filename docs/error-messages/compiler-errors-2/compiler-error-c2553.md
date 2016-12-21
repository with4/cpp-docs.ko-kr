---
title: "컴파일러 오류 C2553 | Microsoft Docs"
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
  - "C2553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2553"
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'base\_function': 재정의 가상 함수의 반환 형식이 'override\_function'과\(와\) 다릅니다.  
  
 파생 클래스의 함수에서 기본 클래스의 가상 함수를 재정의하려고 했지만 파생 클래스 함수의 반환 형식이 기본 클래스 함수의 반환 형식과 다릅니다.  재정의 함수 시그니처는 재정의되는 함수의 시그니처와 일치해야 합니다.  
  
 다음 샘플에서는 C2553 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```