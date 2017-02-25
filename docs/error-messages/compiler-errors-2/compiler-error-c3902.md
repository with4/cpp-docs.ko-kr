---
title: "컴파일러 오류 C3902 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3902"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3902"
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3902
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'accessor': 마지막 매개 변수의 형식은 'type'이어야 합니다.  
  
 적어도 하나의 set 메서드에 대한 마지막 매개 변수의 형식은 속성의 형식과 일치해야 합니다.  자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3902 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3902.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String ^Name {  
      void set(int);   // C3902  
      // try the following line instead  
      // void set(String^){}  
   }  
  
   property double values[int,int] {  
      void set(int, int, float);   // C3902  
      // try the following line instead  
      // void set(int, int, double){}  
   }  
};  
```