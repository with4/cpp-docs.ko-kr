---
title: "컴파일러 오류 C2466 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2466"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2466"
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2466
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상수 크기 0의 배열을 할당할 수 없습니다.  
  
 크기가 0인 배열이 할당 또는 선언되었습니다.  배열 크기에 대한 상수 식은 0보다 큰 정수여야 합니다.  첨자가 0인 배열 선언은 클래스, 구조체 또는 공용 구조체 멤버와 Microsoft 확장\([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\)에서만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2466 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```