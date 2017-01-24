---
title: "컴파일러 오류 C2503 | Microsoft Docs"
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
  - "C2503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2503"
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 기본 클래스는 크기가 0인 배열을 포함할 수 없습니다.  
  
 기본 클래스 또는 구조체에 크기가 0인 배열이 포함됩니다.  클래스의 배열에는 요소가 하나 이상 포함되어야 합니다.  
  
 다음 샘플에서는 C2503 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2503.cpp  
// compile with: /c  
class A {  
   public:  
   int array [];  
};  
  
class B : A {};    // C2503  
  
class C {  
public:  
   int array [10];  
};  
  
class D : C {};  
```