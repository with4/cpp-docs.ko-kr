---
title: "컴파일러 오류 C3900 | Microsoft Docs"
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
  - "C3900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3900"
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 현재 범위에서는 사용할 수 없습니다.  
  
 속성 블록에는 함수 선언과 인라인 함수 정의만 포함될 수 있습니다.  속성 블록에서는 함수를 제외한 어떠한 멤버도 허용되지 않습니다.  형식 정의, 연산자 또는 friend 함수도 허용되지 않습니다.  자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
 이벤트 정의에는 액세스 메서드와 함수만 포함될 수 있습니다.  
  
 다음 샘플에서는 C3900 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 다음 샘플에서는 C3900 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```