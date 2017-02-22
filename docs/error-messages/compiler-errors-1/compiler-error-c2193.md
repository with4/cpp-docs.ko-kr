---
title: "컴파일러 오류 C2193 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2193"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2193"
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2193
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 세그먼트에 이미 있습니다.  
  
 함수가 `alloc_text` 및 `code_seg` pragma를 사용하여 서로 다른 두 세그먼트에 배치되었습니다.  
  
 다음 샘플에서는 C2193 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2193.cpp  
// compile with: /c  
extern "C" void MYFUNCTION();  
#pragma alloc_text(MYCODE, MYFUNCTION)  
#pragma code_seg("MYCODE2")  
extern "C" void MYFUNCTION() {}   // C2193  
extern "C" void MYFUNCTION2() {}  
```