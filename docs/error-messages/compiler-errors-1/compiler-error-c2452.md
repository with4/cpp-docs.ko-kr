---
title: "컴파일러 오류 C2452 | Microsoft Docs"
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
  - "C2452"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2452"
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2452
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : safe\_cast의 소스 형식이 잘못되었습니다.  
  
 [safe\_cast](../../windows/safe-cast-cpp-component-extensions.md)의 소스 형식이 잘못되었습니다.  예를 들어, `safe_cast` 연산에서 모든 형식은 CLR 형식이어야 합니다.  
  
 다음 샘플에서는 C2452 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2452.cpp  
// compile with: /clr  
  
struct A {};  
struct B : public A {};  
  
ref struct C {};  
ref struct D : public C{};  
  
int main() {  
   A a;  
   safe_cast<B*>(&a);   // C2452  
  
   // OK  
   C ^ c = gcnew C;  
   safe_cast<D^>(c);  
}  
```