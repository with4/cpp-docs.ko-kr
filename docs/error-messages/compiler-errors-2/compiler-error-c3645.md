---
title: "컴파일러 오류 C3645 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3645"
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 네이티브 코드로 컴파일된 함수에는 \_\_clrcall을 사용할 수 없습니다.  
  
 함수에 있는 일부 키워드로 인해 함수가 네이티브로 컴파일됩니다.  
  
## 예제  
 다음 샘플에서는 C3645 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```