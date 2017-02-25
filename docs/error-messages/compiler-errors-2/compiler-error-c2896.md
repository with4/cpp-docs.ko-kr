---
title: "컴파일러 오류 C2896 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2896"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2896"
ms.assetid: b600407b-cb05-42e3-9069-2aa6960f0eaa
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2896
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function1' : 'function2' 함수 템플릿을 인수로 사용할 수 없습니다.  
  
 함수 템플릿은 다른 함수 템플릿에 대한 인수가 될 수 없습니다.  
  
 다음 샘플에서는 C2896 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2896.cpp  
template<class T1, class T2> void f1(void(*)(T1, T2));  
template<class T1, class T2> void f2(T1, T2);  
  
int main() {  
   f1(f2);   // C2896  
}  
```  
  
 제네릭을 사용하는 경우에도 C2896이 발생할 수 있습니다.  
  
```  
// C2896b.cpp  
// compile with: /clr  
generic<class T1> void gf1(T1){}  
generic<class T1> void gf2(T1){}  
  
int main() {  
   gf1(gf2);   // C2896  
   gf1(1);   // OK  
}  
```