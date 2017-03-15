---
title: "컴파일러 오류 C2588 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2588"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2588"
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2588
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::~identifier' : 잘못된 전역 소멸자입니다.  
  
 소멸자가 클래스, 구조체 또는 공용 구조체 이외의 대상에 대해 정의되었습니다.  이것은 허용되지 않습니다.  
  
 이 오류는 범위 결정 연산자\(`::`\)의 왼쪽에 클래스, 구조체 또는 공용 구조체 이름이 없는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2588 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2588.cpp  
~F();   // C2588  
```