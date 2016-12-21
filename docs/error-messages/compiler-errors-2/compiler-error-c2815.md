---
title: "컴파일러 오류 C2815 | Microsoft Docs"
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
  - "C2815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2815"
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator delete' : 첫째 정식 매개 변수는 'void \*'이어야 하는데 'param'을\(를\) 사용했습니다.  
  
 사용자 정의 [operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) 함수에서 첫째 정식 매개 변수는 `void *` 형식이어야 합니다.  
  
 다음 샘플에서는 C2815 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```