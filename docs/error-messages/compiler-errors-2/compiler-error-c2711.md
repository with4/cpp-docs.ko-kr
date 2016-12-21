---
title: "컴파일러 오류 C2711 | Microsoft Docs"
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
  - "C2711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2711"
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 이 함수는 관리 코드로 컴파일할 수 없습니다. \#pragma unmanaged를 사용해 보십시오.  
  
 일부 명령에서는 컴파일러가 바깥쪽 함수에 대해 MSIL을 생성하지 못하도록 합니다.  
  
 다음 샘플에서는 C2711 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2711.cpp  
// compile with: /clr  
// processor: x86  
using namespace System;  
value struct V {  
   static const t = 10;  
};  
  
void bar() {  
   V::t;  
   __asm int 3   // C2711 inline asm can't be compiled managed  
}  
```