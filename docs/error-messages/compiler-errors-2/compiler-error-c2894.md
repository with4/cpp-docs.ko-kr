---
title: "컴파일러 오류 C2894 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2894"
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

템플릿에 'C' 링크가 있도록 선언할 수 없습니다.  
  
 이 오류는 `extern` "C" 블록 안에 템플릿을 정의한 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2894 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2894.cpp  
extern "C" {  
   template<class T> class stack {};   // C2894 fail  
  
   template<class T> void f(const T &aT) {}   // C2894  
}  
```  
  
 다음 샘플에서는 C2894 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2894b.cpp  
// compile with: /c  
extern "C" template<class T> void f(const T &aT) {}   // C2894  
  
template<class T> void f2(const T &aT) {}   // OK  
```