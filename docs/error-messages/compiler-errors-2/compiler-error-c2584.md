---
title: "컴파일러 오류 C2584 | Microsoft Docs"
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
  - "C2584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2584"
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Class' : 직접 기본 'Base2'에 액세스할 수 없습니다. 이미 'Base1'의 기본입니다.  
  
 `Class`가 이미 `Base1`에서 직접 파생되었고  `Base2`도 `Base1`에서 파생되었습니다.  `Class`를 `Base2`에서 파생시키는 것은 `Base1`에서 간접적으로 다시 상속하는 것을 의미하므로 불가능합니다. 이는 `Base1`이 이미 직접 기본 클래스이므로 잘못된 것입니다.  
  
## 예제  
 다음 샘플에서는 C2584 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2584.cpp  
// compile with: /c  
struct A1 {  
   virtual int MyFunction();  
};  
  
struct A2 {  
    virtual int MyFunction();  
};  
  
struct B1: public virtual A1, virtual A2 {  
    virtual int MyFunction();  
};  
  
struct B2: public virtual A2, virtual A1 {  
    virtual int MyFunction();  
};  
  
struct C: virtual B1, B2 {  
    virtual int MyFunction();  
};  
  
struct Z : virtual B2, virtual C {   // C2584  
// try the following line insted  
// struct Z : virtual C {  
    virtual int MyFunction();  
};  
```