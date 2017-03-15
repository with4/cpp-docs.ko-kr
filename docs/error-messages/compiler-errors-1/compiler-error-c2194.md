---
title: "컴파일러 오류 C2194 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2194"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2194"
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2194
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 텍스트 세그먼트입니다.  
  
 `data_seg` pragma가 `code_seg`에서 사용되는 세그먼트 이름을 사용합니다.  
  
 다음 샘플에서는 C2194 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2194.cpp  
// compile with: /c  
#pragma code_seg("MYCODE")  
#pragma data_seg("MYCODE")   // C2194  
#pragma data_seg("MYCODE2")   // OK  
```