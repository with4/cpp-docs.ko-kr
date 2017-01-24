---
title: "컴파일러 오류 C3904 | Microsoft Docs"
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
  - "C3904"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3904"
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3904
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property\_accessor': number개의 매개 변수를 지정해야 합니다.  
  
 속성 차원을 기준으로 `get` 및 `set` 메서드의 매개 변수 수를 확인합니다.  
  
-   `get` 메서드의 매개 변수 수는 속성 차원의 수와 같아야 하며, 인덱싱되지 않은 속성의 경우 0이어야 합니다.  
  
-   `set` 메서드의 매개 변수 수는 속성 차원의 수보다 하나 더 많아야 합니다.  
  
 자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3904 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## 예제  
 다음 샘플에서는 C3904 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```