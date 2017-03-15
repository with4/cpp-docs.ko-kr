---
title: "컴파일러 경고 (수준 1) C4348 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4348"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4348"
ms.assetid: 816010eb-6079-48d5-a41b-0fc4d67cfe4c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4348
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 기본 매개 변수 재정의. 매개 변수 number  
  
 템플릿 매개 변수가 재정의되었습니다.  
  
 다음 샘플에서는 C4348 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4348.cpp  
// compile with: /LD /W1  
template <class T=int> struct A;   // forward declaration  
  
template <class T=int> struct A { };   
// C4348, redefinition of default parameter  
// try the following line instead  
// template <class T> struct A { };  
```