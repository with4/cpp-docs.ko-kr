---
title: "컴파일러 경고(수준 1) C4812 | Microsoft Docs"
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
  - "C4812"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4812"
ms.assetid: a7f5721f-2019-44de-ad62-ed30bac8b1f3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4812
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용되지 않는 선언 스타일입니다. 대신 'new\_syntax'를 사용하세요.  
  
 현재 릴리스의 Visual C\+\+에서는 명시적 생성자 특수화가 지원되지만 이후 릴리스에서는 지원되지 않을 수 있습니다.  
  
 다음 샘플에서는 C4812를 생성합니다.  
  
```  
// C4812.cpp // compile with: /W1 /c template <class T> class MyClass; template<class T> class MyClass<T*> { MyClass(); }; template<class T> MyClass<T*>::MyClass<T*>() {}   // C4812 // try the following line instead // MyClass<T*>::MyClass() {}  
```