---
title: "컴파일러 오류 C2824 | Microsoft Docs"
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
  - "C2824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2824"
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator new'의 반환 형식은 'void \*'이어야 합니다.  
  
 비기반 포인터의 경우 `new` 연산자를 오버로드하면 `void *`를 반환해야 합니다.  
  
 다음 샘플에서는 C2824 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2824.cpp  
// compile with: /c  
class   A {  
   A* operator new(size_t i, char *m);   // C2824  
   // try the following line instead  
   // void* operator new(size_t i, char *m);  
};  
```