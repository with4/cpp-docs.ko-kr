---
title: "컴파일러 오류 C3612 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3612"
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': sealed class은\(는\) abstract일 수 없습니다.  
  
 `value`\(또는 [\_\_value](../../misc/value.md)\)로 정의된 형식은 기본적으로 sealed이고, 기본 클래스의 메서드를 모두 구현하지 않는 클래스는 abstract입니다.  sealed이면서 abstract인 클래스는 기본 클래스가 될 수 없고 인스턴스화할 수 없습니다.  
  
 자세한 내용은 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3612 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```