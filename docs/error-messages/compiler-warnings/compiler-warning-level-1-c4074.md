---
title: "컴파일러 경고 (수준 1) C4074 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4074"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4074"
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4074
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이니셜라이저가 컴파일러 예약 초기화 영역에 있습니다.  
  
 [\#pragma init\_seg](../../preprocessor/init-seg.md)에 의해 지정된 컴파일러 초기화 영역이 Microsoft에 의해 예약되었습니다.  이 영역의 코드는 C 런타임 라이브러리의 초기화보다 먼저 실행될 수 있습니다.  
  
 다음 샘플에서는 C4074 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4074.cpp  
// compile with: /W1  
#pragma init_seg( compiler )   // C4074  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```