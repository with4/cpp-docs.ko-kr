---
title: "컴파일러 오류 C3634 | Microsoft Docs"
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
  - "C3634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3634"
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': WinRT 또는 관리되는 클래스의 추상 메서드를 정의할 수 없습니다.  
  
 WinRT 또는 관리되는 클래스에서 추상 메서드를 선언할 수 있지만 정의할 수는 없습니다.  
  
 다음 샘플에서는 C3634 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3634.cpp  
// compile with: /clr  
ref class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```  
  
 **Managed Extensions for C\+\+**  
  
 다음 샘플에서는 C3634 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3634b.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
  
__gc class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```