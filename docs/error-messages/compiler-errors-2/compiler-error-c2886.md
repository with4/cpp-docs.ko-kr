---
title: "컴파일러 오류 C2886 | Microsoft Docs"
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
  - "C2886"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2886"
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2886
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::identifier' : 멤버 using 선언에서 기호를 사용할 수 없습니다.  
  
 `using` 선언에는 네임스페이스 이름 같은 기호가 사용됩니다.  `using` 선언은 기본 클래스 멤버 선언을 위한 것입니다.  
  
 다음 샘플에서는 C2886 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2886.cpp  
// compile with: /c  
namespace Z {  
    int i;  
}  
  
class B {  
protected:  
    int i;  
};  
  
class D : public B {  
    // Error: Z is a namespace  
    using Z::i;   // C2886  
  
    // OK: B is a base class  
    using B::i;  
};  
```