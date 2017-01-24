---
title: "컴파일러 오류 C2332 | Microsoft Docs"
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
  - "C2332"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2332"
ms.assetid: fb05cd68-e271-4bea-9fb7-ef4edb0a26ac
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2332
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typedef' : 태그 이름이 없습니다.  
  
 컴파일러가 완성되지 않은 형식 정의를 발견했습니다.  
  
 다음 샘플에서는 C2332 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2332.cpp  
// compile with: /c  
struct S {  
   int i;  
};  
  
typedef struct * pS;   // C2332  
typedef struct S* pS;   // OK  
  
int get_S_i(pS p) {  
   return p->i;  
}  
```