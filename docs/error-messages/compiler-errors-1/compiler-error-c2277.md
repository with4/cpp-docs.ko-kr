---
title: "컴파일러 오류 C2277 | Microsoft Docs"
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
  - "C2277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2277"
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 이 멤버 함수의 주소를 가져올 수 없습니다.  
  
 멤버 함수의 주소를 가져올 수 없습니다.  
  
 다음 샘플에서는 C2277 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2277.cpp  
class A {  
public:  
   A();  
};  
(*pctor)() = &A::A;   // C2277   
```