---
title: "컴파일러 오류 C3804 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3804"
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 오류 C3804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property\_accessor': 속성에 대한 접근자 메서드는 모두 static이거나 모두 static이 아니어야 합니다.  
  
 특수한 속성을 정의할 때 접근자 함수는 정적이거나 인스턴스일 수 있지만 둘 다 포함할 수는 없습니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3804 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3804.cpp  
// compile with: /c /clr  
ref struct A {  
  
   property int i {  
      static int get() {}  
      void set(int i) {}  
   }   // C3804 error  
  
   // OK  
   property int j {  
      int get() { return 0; }  
      void set(int i) {}  
   }  
  
   property int k {  
      static int get() { return 0; }  
      static void set(int i) {}  
   }  
};  
```