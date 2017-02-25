---
title: "컴파일러 오류 C2640 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2640"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2640"
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2640
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : \_\_based 한정자를 참조로 사용할 수 없습니다.  
  
 `__based` 한정자는 포인터에만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2640 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2640.cpp  
void f(int i) {  
    void *vp;  
    int _based(vp) &vr = I;  // C2640  
}  
```