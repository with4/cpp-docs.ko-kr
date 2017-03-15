---
title: "컴파일러 오류 C3903 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3903"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3903"
ms.assetid: cf47d7ad-a3bd-4f75-a253-71586e7a3be6
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3903
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property': set 또는 get 메서드가 없습니다.  
  
 속성에 적어도 하나의 `get` 또는 `set` 메서드가 있어야 합니다.  자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3903 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3903.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void f(int){}  
      // Add one or both of the following lines.  
      // void set(int){}  
      // int get(){return 0;}  
   };   // C3903  
  
   property double Q[,,,,] {  
      void f(){}  
      // Add one or both of the following lines.  
      // void set(int, char, int, char, double, double){}  
      // double get(int, char, int, char, double){return 1.1;}  
   }   // C3903  
};  
```