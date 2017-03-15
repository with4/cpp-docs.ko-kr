---
title: "컴파일러 오류 C2528 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2528"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2528"
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2528
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 참조에 대한 포인터가 잘못되었습니다.  
  
 참조에 대한 포인터를 선언할 수 없습니다.  참조에 대한 포인터를 선언하기 전에 변수를 역참조하십시오.  
  
 다음 샘플에서는 C2528 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2528.cpp  
int i;  
int &ir = i;  
int & (*irptr) = ir;    // C2528  
```