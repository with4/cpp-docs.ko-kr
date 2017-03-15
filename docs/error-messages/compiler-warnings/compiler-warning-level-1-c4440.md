---
title: "컴파일러 경고 (수준 1) C4440 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4440"
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4440
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'calling\_convention1'에서 'calling\_convention2'\(으\)로 재정의된 호출 규칙이 무시됩니다.  
  
 호출 규칙을 변경하려는 시도가 무시되었습니다.  
  
 다음 샘플에서는 C4440 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4440.cpp  
// compile with: /W1 /LD /clr  
typedef void __clrcall F();  
typedef F __cdecl *PFV;   // C4440  
```