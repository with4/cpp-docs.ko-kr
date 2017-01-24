---
title: "컴파일러 오류 C2208 | Microsoft Docs"
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
  - "C2208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2208"
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 이 형식을 사용하여 정의된 멤버가 없습니다.  
  
 형식 이름으로 확인되는 식별자가 집계 선언에 있으나 컴파일러에서 멤버를 선언할 수 없습니다.  
  
 다음 샘플에서는 C2208 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2208.cpp  
class C {  
   C;   // C2208  
   C(){}   // OK  
};  
```