---
title: "컴파일러 오류 C3644 | Microsoft Docs"
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
  - "C3644"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3644"
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3644
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수를 컴파일하여 관리 코드를 생성할 수 없습니다.  
  
 함수에 있는 일부 키워드로 인해 함수가 네이티브로 컴파일됩니다.  
  
 다음 샘플에서는 C3644 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3644.cpp  
// compile with: /clr  
// processor: x86  
  
void __clrcall Func2(int i) {  
   __asm {}   // C3644  
}  
```