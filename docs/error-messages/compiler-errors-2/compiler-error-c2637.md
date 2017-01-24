---
title: "컴파일러 오류 C2637 | Microsoft Docs"
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
  - "C2637"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2637"
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2637
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 데이터 멤버에 대한 포인터를 수정할 수 없습니다.  
  
 데이터 멤버에 대한 포인터에 호출 규칙을 적용할 수 없습니다.  이 문제를 해결하려면 호출 규칙을 제거하거나 멤버 함수에 대한 포인터를 선언해야 합니다.  
  
 다음 샘플에서는 C2637 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2637.cpp  
// compile with: /c  
struct S {};  
int __stdcall S::*pms1;   // C2637  
  
// OK  
int S::*pms2;  
int (__stdcall S::*pms3)(...);  
```