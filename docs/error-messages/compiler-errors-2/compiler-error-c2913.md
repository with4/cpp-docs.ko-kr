---
title: "컴파일러 오류 C2913 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2913"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2913"
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2913
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명시적 특수화. 'declaration'이\(가\) 클래스 템플릿의 특수화가 아닙니다.  
  
 비템플릿 클래스를 특수화할 수 없습니다.  
  
 다음 샘플에서는 C2913 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2913.cpp  
// compile with: /c  
class X{};  
template <class T> class Y{};  
  
template<> class X<int> {};   // C2913  
template<> class Y<int> {};  
```