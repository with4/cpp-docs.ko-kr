---
title: "컴파일러 오류 C3626 | Microsoft Docs"
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
  - "C3626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3626"
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword': '\_\_event' 키워드는 대리자에 대한 포인터인 데이터 멤버, 멤버 함수 및 COM 인터페이스에서만 사용될 수 있습니다.  
  
 키워드를 잘못 사용했습니다.  
  
 다음 샘플에서는 C3626 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```