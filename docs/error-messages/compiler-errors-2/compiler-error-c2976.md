---
title: "컴파일러 오류 C2976 | Microsoft Docs"
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
  - "C2976"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2976"
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2976
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 형식 인수가 너무 적습니다.  
  
 제네릭 또는 템플릿에 하나 이상의 실제 인수가 없습니다.  제네릭 또는 템플릿 선언을 확인하여 매개 변수의 올바른 개수를 알아보십시오.  
  
 이 오류는 STL 구성 요소에 템플릿 인수가 없는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2976 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2976.cpp  
template <class T>   
struct TC {  
   T t;  
};  
int main() {  
   TC<>* t;   // C2976  
   TC<int>* t2;   // OK  
}  
```  
  
 제네릭을 사용하는 경우에도 C2976이 발생할 수 있습니다.  
  
```  
// C2976b.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC {  
   T t;  
};  
  
int main() {  
   GC<>^ g;   // C2976  
   GC<int>^ g2;   // OK  
}  
```