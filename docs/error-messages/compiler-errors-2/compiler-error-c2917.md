---
title: "컴파일러 오류 C2917 | Microsoft Docs"
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
  - "C2917"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2917"
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2917
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': 템플릿\-매개 변수가 잘못되었습니다.  
  
 템플릿 매개 변수 목록에 템플릿 매개 변수가 아닌 식별자가 포함되어 있습니다.  
  
## 예제  
 다음 샘플에서는 C2917을 생성합니다.  
  
```  
// C2917.cpp // compile with: /c template<class T> class Vector { void sort(); }; template<class T*> void Vector<T>::sort() {}   // C2917 // try the following line instead // template<class T> void Vector<T>::sort() {}  
```