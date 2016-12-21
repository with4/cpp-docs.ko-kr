---
title: "컴파일러 오류 C3798 | Microsoft Docs"
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
  - "C3798"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3798"
ms.assetid: b2f8b1d8-8812-49b8-a346-28e48f02ba5c
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3798
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier': 속성 선언에는 재정의 지정자를 사용할 수 없습니다. 재정의 지정자는 속성 get\/set 메서드에 사용해야 합니다.  
  
 속성이 잘못 선언되었습니다.  자세한 내용은 다음을 참조하십시오.  
  
-   [property](../../windows/property-cpp-component-extensions.md)  
  
-   [abstract](../../windows/abstract-cpp-component-extensions.md)  
  
-   [sealed](../../windows/sealed-cpp-component-extensions.md)  
  
## 예제  
 다음 샘플에서는 C3798 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C3798.cpp  
// compile with: /clr /c  
ref struct A {  
   property int Prop_1 abstract;   // C3798  
   property int Prop_2 sealed;   // C3798  
  
   // OK  
   property int Prop_3 {  
      virtual int get() abstract;  
      virtual void set(int i) abstract;  
   }  
  
   property int Prop_4 {  
      virtual int get() sealed;  
      virtual void set(int i) sealed;  
   }  
};  
```