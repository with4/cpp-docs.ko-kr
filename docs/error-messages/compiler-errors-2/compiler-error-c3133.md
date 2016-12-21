---
title: "컴파일러 오류 C3133 | Microsoft Docs"
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
  - "C3133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3133"
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ varargs에 특성을 적용할 수 없습니다.  
  
 특성을 잘못 적용했습니다.  가변 인수를 나타내는 가변 매개 변수\(...\)에는 특성을 적용할 수 없습니다.  
  
 자세한 내용은 [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3133 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3133.cpp  
// compile with: /clr /c  
ref struct MyAttr: System::Attribute {};   
void Func([MyAttr]...);   // C3133  
void Func2([MyAttr] int i);   // OK  
```