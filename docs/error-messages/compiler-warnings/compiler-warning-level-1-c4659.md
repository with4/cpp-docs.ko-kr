---
title: "컴파일러 경고 (수준 1) C4659 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4659"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4659"
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4659
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma 'pragma' : 예약된 세그먼트 'segment'에 정의되지 않은 동작이 있습니다. \#pragma comment\(linker, ...\)를 사용하십시오.  
  
 옵션을 링커에 전달하는 데 .drectve 옵션을 사용했습니다.  링커 옵션을 전달하려면 대신 pragma [comment](../../preprocessor/comment-c-cpp.md)을 사용하십시오.  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```