---
title: "컴파일러 오류 C2493 | Microsoft Docs"
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
  - "C2493"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2493"
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2493
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_based의 형식이 올바르지 않습니다.  
  
 `__based` 식은 포인터를 기반으로 해야 합니다.  
  
 다음 샘플에서는 C2493 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2493.cpp  
// compile with: /c  
char mybase;  
int __based(mybase) ptr;   // C2493  
  
// OK  
char * mybase;  
int __based(mybase) * ptr;  
```