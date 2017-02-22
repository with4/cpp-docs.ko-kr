---
title: "컴파일러 경고 (수준 1) C4550 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4550"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4550"
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4550
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

식이 인수 목록이 없는 함수로 계산됩니다.  
  
 함수에 대해 참조되지 않은 포인터에 인수 목록이 없습니다.  
  
## 예제  
  
```  
// C4550.cpp  
// compile with: /W1  
bool f()  
{  
   return true;  
}  
  
typedef bool (*pf_t)();  
  
int main()  
{  
   pf_t pf = f;  
   if (*pf) {}  // C4550  
   return 0;  
}  
```