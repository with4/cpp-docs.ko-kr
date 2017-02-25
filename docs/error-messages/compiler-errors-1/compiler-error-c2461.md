---
title: "컴파일러 오류 C2461 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2461"
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 생성자 구문에 정식 매개 변수가 없습니다.  
  
 클래스의 생성자에 정식 매개 변수가 지정되지 않았습니다.  생성자의 선언에 정식 매개 변수를 지정해야 합니다. 이 목록은 Null이 될 수 있습니다.  
  
 `class` `::` `class` 다음에 한 쌍의 괄호를 추가하십시오.  
  
 다음 샘플에서는 C2461 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;   // C2461  
   C::C();   // OK  
};  
```