---
title: "컴파일러 오류 C3219 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3219"
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param': 제네릭 매개 변수는 여러 개의 비인터페이스\('class'\)에 의해 제약을 받을 수 없습니다.  
  
 제네릭 매개 변수를 둘 이상의 관리되는 클래스로 제한할 수 없습니다.  
  
 다음 샘플에서는 C3219를 생성합니다.  
  
```  
// C3219.cpp // compile with: /clr ref class A {}; ref class B {}; generic <class T> where T : A, B ref class E {};   // C3219  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3219b.cpp // compile with: /clr /c ref class A {}; interface struct C {}; generic <class T> where T : A ref class E {};  
```