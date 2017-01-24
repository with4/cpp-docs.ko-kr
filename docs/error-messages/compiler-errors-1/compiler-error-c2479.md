---
title: "컴파일러 오류 C2479 | Microsoft Docs"
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
  - "C2479"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2479"
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2479
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 'allocate\( \)'는 정적 범위의 데이터 항목에만 유효합니다.  
  
 `__declspec( allocate())` 구문은 정적 데이터에만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2479 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2479.cpp  
// compile with: /c  
#pragma section("mycode", read)  
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479  
__declspec(allocate("mycode"))  int i = 0;   // OK  
```