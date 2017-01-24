---
title: "컴파일러 오류 C2213 | Microsoft Docs"
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
  - "C2213"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2213"
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2213
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'modifier' : \_\_based에 대한 인수가 잘못되었습니다.  
  
 `__based`를 수정하는 인수가 잘못되었습니다.  
  
 다음 샘플에서는 C2213 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2213.cpp  
// compile with: /c  
int i;  
int *j;  
char __based(i) *p;   // C2213  
char __based(j) *p2;   // OK  
```