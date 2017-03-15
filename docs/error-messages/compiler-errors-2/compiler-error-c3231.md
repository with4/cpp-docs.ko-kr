---
title: "컴파일러 오류 C3231 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3231"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3231"
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3231
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : 템플릿 형식 인수는 제네릭 형식 매개 변수를 사용할 수 없습니다.  
  
 템플릿은 컴파일할 때 인스턴스화되지만 제네릭은 런타임에 인스턴스화됩니다.  따라서 템플릿을 호출하는 제네릭 코드를 생성할 수 없습니다. 제네릭 형식이 최종적으로 결정되는 런타임에 템플릿을 인스턴스화할 수 없기 때문입니다.  
  
 다음 샘플에서는 C3231 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3231.cpp  
// compile with: /clr /LD  
template <class T> class A;  
  
generic <class T>  
ref class C {  
   void f() {  
      A<T> a;   // C3231  
   }  
};  
```