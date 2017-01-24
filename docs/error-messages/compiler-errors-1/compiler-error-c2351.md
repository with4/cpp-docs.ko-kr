---
title: "컴파일러 오류 C2351 | Microsoft Docs"
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
  - "C2351"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2351"
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2351
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용되지 않는 C\+\+ 생성자 초기화 구문입니다.  
  
 생성자에 대한 새로운 스타일 초기화 목록에서는 기본 클래스가 하나이더라도 직접적인 각 기본 클래스의 이름을 명시적으로 지정해야 합니다.  
  
 다음 샘플에서는 C2351 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```