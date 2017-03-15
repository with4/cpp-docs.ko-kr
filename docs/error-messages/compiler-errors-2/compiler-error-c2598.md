---
title: "컴파일러 오류 C2598 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2598"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2598"
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2598
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링크 사양은 전역 범위에 있어야 합니다.  
  
 링크 지정자가 지역 범위에서 선언되었습니다.  
  
 다음 샘플에서는 C2598 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2598.cpp  
// compile with: /c  
void func() {  
   extern "C" int func2();   // C2598  
}  
  
extern "C" int func( int i );  
```