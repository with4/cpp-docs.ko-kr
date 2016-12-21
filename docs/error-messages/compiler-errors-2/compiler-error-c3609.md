---
title: "컴파일러 오류 C3609 | Microsoft Docs"
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
  - "C3609"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3609"
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3609
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 봉인 함수 또는 최종 함수는 virtual이어야 합니다.  
  
 [sealed](../../windows/sealed-cpp-component-extensions.md) 및 [final](../../cpp/final-specifier.md) 키워드는 `virtual`로 표시된 클래스, 구조체 또는 멤버 함수에 대해서만 사용할 수 있습니다.  
  
 다음 샘플에서는 C3609 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  
  
 **Managed Extensions for C\+\+**  
  
 다음 샘플에서는 C3609 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3609c.cpp  
// compile with: /clr:oldSyntax /c  
__gc class C {  
   __sealed int f();   // C3609  
   __sealed virtual int f2();   // OK  
};  
```