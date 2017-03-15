---
title: "컴파일러 오류 C2784 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2784"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2784"
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2784
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration': 'type'의 템플릿 인수를 'type'에서 추론할 수 없습니다.  
  
 컴파일러가 제공된 함수 인수에서 템플릿 인수를 확인할 수 없습니다.  
  
 다음 샘플에서는 C2784를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2784.cpp  
template<class T> class X {};  
template<class T> void f(X<T>) {}  
  
int main() {  
   X<int> x;  
   f(1);   // C2784  
  
   // To fix it, try the following line instead  
   f(x);  
}  
```