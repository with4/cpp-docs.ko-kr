---
title: "컴파일러 경고 (수준 1) C4489 | Microsoft Docs"
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
  - "C4489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4489"
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier' : 인터페이스 메서드 'method'에 사용할 수 없습니다. 지정자 재정의는 ref 클래스와 값 클래스 메서드에만 허용됩니다.  
  
 인터페이스 메서드에 지정자 키워드를 올바르지 않게 사용했습니다.  
  
 자세한 내용은 [Override 지정자](../../windows/override-specifiers-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4489 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4489.cpp  
// compile with: /clr /c /W1  
public interface class I {   
   void f() new;   // C4489  
   virtual void b() override;   // C4489  
  
   void g();   // OK  
};  
```