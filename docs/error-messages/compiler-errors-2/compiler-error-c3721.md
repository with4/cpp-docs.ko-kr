---
title: "컴파일러 오류 C3721 | Microsoft Docs"
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
  - "C3721"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3721"
ms.assetid: c696ca38-3e00-4875-abbe-7bce0f46930e
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3721
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'signature': 이벤트에 대한 시그니처가 호환되지 않습니다.  
  
 이벤트가 잘못 선언되었습니다.  자세한 내용은 [\_\_event](../../cpp/event.md)를 참조하십시오.  
  
 C3721은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
## 예제  
 다음 샘플에서는 C3721 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3721.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
  
public __delegate void MyDel();  
  
public __gc class X {  
   __event void add_E1();      // C3721  
   // try the following line instead  
   // __event void add_E1(MyDel * p);  
  
   __event void remove_E1();   // C3721  
   // __event void remove_E1(MyDel * p);  
   // try the following line instead  
  
   __event void raise_E1();  
};  
```