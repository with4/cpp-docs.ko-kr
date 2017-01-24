---
title: "컴파일러 오류 C3901 | Microsoft Docs"
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
  - "C3901"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3901"
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3901
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'accessor\_function': 반환 형식이 'type'이어야 합니다.  
  
 적어도 하나 이상의 get 메서드 반환 형식이 속성 형식과 일치해야 합니다.  자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3901 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3901.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String^ Name {  
      void get();   // C3901  
      // try the following line instead  
      // String^ get();  
   };  
};  
  
ref class Y {  
   property double values[int, int] {  
      int get(int, int);   // C3901  
      // try the following line instead  
      // double get(int, int);  
   };  
};  
```