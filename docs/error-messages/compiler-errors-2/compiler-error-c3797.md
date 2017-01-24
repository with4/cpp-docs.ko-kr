---
title: "컴파일러 오류 C3797 | Microsoft Docs"
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
  - "C3797"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3797"
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3797
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override': 이벤트 선언에는 재정의 지정자를 사용할 수 없습니다. 재정의 지정자는 이벤트 add\/remove\/raise 메서드에 사용해야 합니다.  
  
 trivial 이벤트\(명시적으로 정의된 접근자 메서드가 없는 이벤트\)를 다른 trivial 이벤트로 재정의할 수 없습니다.  재정의하는 이벤트에서는 접근자 함수로 동작을 정의해야 합니다.  
  
 자세한 내용은 [event](../../windows/event-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3797 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```