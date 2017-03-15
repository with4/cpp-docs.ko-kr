---
title: "컴파일러 오류 C2811 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2811"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2811"
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2811
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' : 'type2'에서 상속될 수 없습니다. ref 클래스은\(는\) ref 클래스 또는 인터페이스 클래스에서만 상속될 수 있습니다.  
  
 관리되지 않는 클래스를 관리되는 클래스의 기본 클래스로 사용하려고 했습니다.  
  
 다음 샘플에서는 C2811 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2811.cpp  
// compile with: /clr /c  
struct S{};  
ref struct T {};  
ref class C : public S {};   // C2811  
ref class D : public T {};   // OK  
```