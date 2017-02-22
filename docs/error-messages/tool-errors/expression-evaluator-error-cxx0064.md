---
title: "식 계산기 오류 CXX0064 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0064"
  - "CXX0064"
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 식 계산기 오류 CXX0064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

바인딩된 가상 멤버 함수에 중단점을 설정할 수 없습니다.  
  
 중단점이 개체에 대한 포인터를 통해 가상 멤버 함수에 설정되어 있습니다. 예:  
  
```  
pClass->vfunc( int );  
```  
  
 클래스를 입력하여 가상 함수에 중단점을 설정할 수 있습니다. 예:  
  
```  
Class::vfunc( int );  
```  
  
 이 오류는 CAN0064와 동일합니다.