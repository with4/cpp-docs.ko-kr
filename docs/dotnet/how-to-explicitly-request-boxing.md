---
title: "방법: 명시적으로 boxing 요청 | Microsoft Docs"
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
  - "boxing, 명시적 요청"
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 방법: 명시적으로 boxing 요청
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자는 변수를 형식 `Object` 변수에 할당하는 것으로 boxing을 명시적으로 요청할 수 있습니다.  
  
## 예제  
  
```  
// vcmcppv2_explicit_boxing3.cpp  
// compile with: /clr  
using namespace System;  
  
void f(int i) {  
   Console::WriteLine("f(int i)");  
}  
  
void f(Object ^o) {  
   Console::WriteLine("f(Object^ o)");  
}  
  
int main() {  
   int i = 5;  
   Object ^ O = i;   // forces i to be boxed  
   f(i);  
   f(O);  
   f( (Object^)i );  // boxes i  
}  
```  
  
  **f\(int i\)**  
**f\(Object^ o\)**  
**f\(Object^ o\)**   
## 참고 항목  
 [Boxing](../windows/boxing-cpp-component-extensions.md)