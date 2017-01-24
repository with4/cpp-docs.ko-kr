---
title: "컴파일러 오류 C2611 | Microsoft Docs"
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
  - "C2611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2611"
ms.assetid: 3f2d5253-f24f-4724-83d0-6b2aa6a4e551
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token' : '~' 다음에 사용할 수 없습니다. 식별자가 필요합니다.  
  
 토큰이 식별자가 아닙니다.  
  
 다음 샘플에서는 C2611 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2611.cpp  
// compile with: /c  
class C {  
   C::~operator int();   // C2611  
   ~C();   // OK  
};  
```