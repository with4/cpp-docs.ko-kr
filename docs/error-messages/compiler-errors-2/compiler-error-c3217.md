---
title: "컴파일러 오류 C3217 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3217"
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param': 제네릭 매개 변수는 이 선언에서 제약을 받을 수 없습니다.  
  
 제약 조건의 형식이 잘못되었습니다. 제약 조건 제네릭 매개 변수는 제네릭 클래스 템플릿 매개 변수와 일치해야 합니다.  
  
 다음 샘플에서는 C3217을 생성합니다.  
  
```  
// C3217.cpp // compile with: /clr interface struct A {}; generic <class T> ref class C { generic <class T1> where T : A   // C3217 void f(); };  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3217b.cpp // compile with: /clr /c interface struct A {}; generic <class T> ref class C { generic <class T1> where T1 : A void f(); };  
```