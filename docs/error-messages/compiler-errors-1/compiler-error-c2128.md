---
title: "컴파일러 오류 C2128 | Microsoft Docs"
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
  - "c2128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2128"
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : alloc\_text\/same\_seg는 C 링크가 있는 함수에만 적용할 수 있습니다.  
  
 `pragma` `alloc_text` 는 C 링크를 포함하도록 선언된 함수에만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2128 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2128.cpp  
// compile with: /c  
  
// Delete the following line to resolve.  
void func();  
// #pragma alloc_text("my segment", func)   // C2128  
  
extern "C" {  
void func();  
}  
  
#pragma alloc_text("my segment", func)  
void func() {}  
```