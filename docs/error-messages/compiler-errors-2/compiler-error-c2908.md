---
title: "컴파일러 오류 C2908 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2908"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2908"
ms.assetid: 49cd2a21-cad8-4ba0-9a0b-3a0190d9344c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2908
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명시적 특수화. 'template'이\(가\) 이미 인스턴스화되어 있습니다.  
  
 기본 템플릿의 특수화가 명시적 특수화보다 먼저 발생했습니다.  
  
 다음 샘플에서는 C2908 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2908.cpp  
// compile with: /c  
template<class T> class X {};  
  
void f() {  
X<int> x;   //specialization and instantiation  
            //of X<int>  
}  
  
template<> class X<int> {}  // C2908, explicit specialization  
```