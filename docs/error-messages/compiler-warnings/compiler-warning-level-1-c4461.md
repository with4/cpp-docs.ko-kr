---
title: "컴파일러 경고(수준 1) C4461 | Microsoft Docs"
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
  - "C4461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4461"
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 이 클래스에는 'finalizer' 종료자가 있지만 'dtor' 소멸자가 없습니다.  
  
 형식에 종료자가 있다는 것은 삭제할 리소스가 있음을 의미합니다.  형식의 소멸자에서 종료자를 명시적으로 호출하지 않으면 개체가 범위를 벗어난 후에 공용 언어 런타임이 종료자를 실행할 시기를 결정합니다.  
  
 형식에 소멸자를 정의하고 소멸자에서 종료자를 명시적으로 호출하면 종료자를 명확하게 실행할 수 있습니다.  
  
 자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4461 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```