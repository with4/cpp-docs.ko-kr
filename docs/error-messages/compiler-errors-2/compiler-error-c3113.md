---
title: "컴파일러 오류 C3113 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3113"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3113"
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3113
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'structure'은\(는\) 템플릿\/제네릭일 수 없습니다.  
  
 인터페이스나 열거형을 사용하여 클래스 템플릿 또는 클래스 제네릭을 만들려고 했습니다.  
  
 다음 샘플에서는 C3113 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```