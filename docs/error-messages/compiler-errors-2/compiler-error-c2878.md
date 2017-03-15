---
title: "컴파일러 오류 C2878 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2878"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2878"
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2878
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 같은 이름을 가진 네임스페이스 또는 클래스가 없습니다.  
  
 정의되지 않은 네임스페이스 또는 클래스를 참조했습니다.  
  
 다음 샘플에서는 C2878 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2878.cpp  
// compile with: /c  
namespace A {}  
namespace B = C;   // C2878 namespace C doesn't exist  
namespace B = A;   
```