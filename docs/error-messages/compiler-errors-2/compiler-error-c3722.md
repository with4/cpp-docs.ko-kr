---
title: "컴파일러 오류 C3722 | Microsoft Docs"
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
  - "C3722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3722"
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제네릭 이벤트는 사용할 수 없습니다.  
  
 컴파일러에서는 제네릭 클래스, 구조체 및 함수만 허용됩니다.  자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3722 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3722.cpp  
// compile with: /clr  
generic <typename T>  
public delegate void MyEventHandler(System::Object^ sender, System::EventArgs^ e, T optional);  
  
generic <class T>  
public ref struct MyButton {  
   generic<typename U>  
   event MyEventHandler<U>^ Click;   // C3722  
};  
```