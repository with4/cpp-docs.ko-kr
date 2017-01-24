---
title: "컴파일러 오류 C2614 | Microsoft Docs"
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
  - "C2614"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2614"
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2614
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class1' : 멤버 초기화가 잘못되었습니다. 'class2'이\(가\) 기본 또는 멤버가 아닙니다.  
  
 멤버 또는 기본 클래스만 클래스 또는 구조체에 대한 초기화 목록에 표시할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C2614 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2614.cpp  
// compile with: /c  
struct A {  
   int i;  
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A  
};  
  
struct A2 {  
   int B;  
   int i;  
   A2( int ia ) : B( i ) {};   // OK  
};  
```