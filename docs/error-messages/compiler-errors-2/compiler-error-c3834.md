---
title: "컴파일러 오류 C3834 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3834"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3834"
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3834
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

고정된 포인터로 명시적으로 잘못 캐스팅했습니다. 고정된 지역 변수를 대신 사용하십시오.  
  
 고정된 포인터로 명시적으로 캐스팅할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3834 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3834.cpp  
// compile with: /clr  
int main() {  
   int x = 33;  
  
   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834  
   pin_ptr<int> p2 = &x;   // OK  
}  
```  
  
## 예제  
 다음 샘플에서는 C3834 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3834_b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
  
int main() {  
   const __wchar_t * pS = reinterpret_cast<const __wchar_t __pin*>(S"hello");   // C3834  
  
   // OK   
   // declare a pinning variable  
   String __pin* ppin = S"Hello";  
  
   // cast pinning variable to unmanaged type  
   const __wchar_t * pS2 = reinterpret_cast<__wchar_t*>(ppin);     
  
   pS2 += 6;  
}  
```