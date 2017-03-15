---
title: "컴파일러 경고 (수준 3) C4570 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4570"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4570"
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 3) C4570
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 명시적으로 추상으로 선언되지 않았지만 추상 함수를 가지고 있습니다.  
  
 [abstract](../../windows/abstract-cpp-component-extensions.md) 함수가 포함된 형식은 그 자체가 추상으로 표시되어야 합니다.  
  
## 예제  
 다음 샘플에서는 C4570 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4570.cpp  
// compile with: /clr /W3 /c  
ref struct X {   // C4570  
// try the following line instead  
// ref class X abstract {  
   virtual void f() abstract;  
};  
```