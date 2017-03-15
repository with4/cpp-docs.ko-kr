---
title: "방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boxing, implicit"
  - "gcnew 키워드[C++], 값 형식 만들기"
  - "값 형식, 만들기"
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Using [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) on a value type will create a boxed value type, which can then be placed on the managed, garbage\-collected heap.  
  
## 예제  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## 참고 항목  
 [Boxing](../windows/boxing-cpp-component-extensions.md)