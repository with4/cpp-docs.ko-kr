---
title: "표준 변환 및 암시적 boxing | Microsoft Docs"
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
ms.assetid: 33f7fc7d-5674-44a2-a859-0e6a04fae519
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# 표준 변환 및 암시적 boxing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A standard conversion will be chosen by the compiler over a conversion that requires boxing.  
  
## 예제  
  
```  
// clr_implicit_boxing_Std_conversion.cpp  
// compile with: /clr  
int f3(int ^ i) {   // requires boxing  
   return 1;  
}  
  
int f3(char c) {   // no boxing required, standard conversion  
   return 2;  
}  
  
int main() {  
   int i = 5;  
   System::Console::WriteLine(f3(i));  
}  
```  
  
 **2**   
## 참고 항목  
 [Boxing](../windows/boxing-cpp-component-extensions.md)