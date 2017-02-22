---
title: "컴파일러 오류 C3114 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3114"
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3114
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'argument': 명명된 특성 인수가 잘못되었습니다.  
  
 특성 클래스 데이터 멤버를 유효하게 명명된 인수로 사용하려면 `static`, `const` 또는 `literal`로 표시하지 말아야 합니다.  속성의 경우 이 속성은 `static`이 아니어야 하고 get 및 set 접근자가 있어야 합니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 및 [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3114 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```