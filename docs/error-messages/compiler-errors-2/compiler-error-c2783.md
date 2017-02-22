---
title: "컴파일러 오류 C2783 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2783"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2783"
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# 컴파일러 오류 C2783
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration' : 'identifier'의 템플릿 인수를 추론할 수 없습니다.  
  
 컴파일러가 템플릿 인수를 확인할 수 없습니다.  기본 인수는 템플릿 인수를 추론하는 데 사용할 수 없습니다.  
  
 다음 샘플에서는 C2783 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2783.cpp  
template<typename T1, typename T2>  
T1 f(T2) {  
   return 248;  
}  
  
int main() {  
   f(1);   // C2783  
   // try the following line instead  
   int i = f<int>(1);  
}  
```  
  
 제네릭을 사용하는 경우에도 C2783이 발생할 수 있습니다.  
  
```  
// C2783b.cpp  
// compile with: /clr  
using namespace System;  
generic<typename T1, typename T2>   
T1 gf(T2) {  
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));  
   return t1;  
}  
  
ref class MyClass{};  
  
int main() {  
   int i;  
   i = gf(9);   // C2783  
  
   // OK  
   i = gf<int>(9);  
}  
```