---
title: "컴파일러 오류 C2974 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2974"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2974"
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2974
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'number'의 형식 인수가 잘못되었습니다. 형식이 필요합니다.  
  
 제네릭 또는 템플릿 인수가 제네릭 또는 템플릿 선언과 일치하지 않습니다.  형식은 꺾쇠 괄호로 묶어야 합니다.  제네릭 또는 템플릿 정의를 확인하여 올바른 형식을 알아보십시오.  
  
 다음 샘플에서는 C2974 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2974.cpp  
// C2974 expected  
template <class T>  
struct TC {};  
  
template <typename T>  
void tf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   TC<1>* tc;  
   tf<"abc">("abc");  
  
   TC<int>* tc;  
   tf<const char *>("abc");  
}  
```  
  
 제네릭을 사용하는 경우에도 C2974가 발생할 수 있습니다.  
  
```  
// C2974b.cpp  
// compile with: /clr  
// C2974 expected  
using namespace System;  
generic <class T>  
ref struct GCtype {};  
  
generic <typename T>  
void gf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   GCtype<"a">^ gc;  
   gf<"a">("abc");  
  
   // OK  
   GCtype<int>^ gc;  
   gf<String ^>("abc");  
}  
```