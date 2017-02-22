---
title: "컴파일러 오류 C3648 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3648"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3648"
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3648
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 명시적 재정의 구문에는 \/clr:oldSyntax가 필요합니다.  
  
 최신 버전의 관리되는 구문에 대한 컴파일을 진행하는 동안 컴파일러가 이전 버전에 대한 명시적 재정의 구문을 발견했습니다.  
  
 자세한 내용은 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  이전 버전의 구문에 대한 자세한 내용은 [명시적으로 재정의](../../cpp/explicit-overrides-cpp.md)를 참조하십시오.  
  
 다음 샘플에서는 C3648 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3648.cpp  
// compile with: /clr  
public interface struct I {  
   void f();  
};  
  
public ref struct R : I {  
   virtual void I::f() {}   // C3648  
   // try the following line instead  
   // virtual void f() = I::f{}  
};  
```