---
title: "컴파일러 오류 C2383 | Microsoft Docs"
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
  - "C2383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2383"
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 이 기호에는 기본 인수를 사용할 수 없습니다.  
  
 C\+\+ 컴파일러에서는 함수에 대한 포인터에 기본 인수를 사용할 수 없습니다.  
  
 이전 버전의 컴파일러에서는 이 코드를 사용할 수 있지만 현재 버전에서는 오류가 발생합니다.  모든 버전의 Visual C\+\+에서 코드가 작동하도록 하려면 함수 포인터 인수에 기본값을 할당하지 마십시오.  
  
 다음 줄은 C2383를 발생시킵니다.  
  
```  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```