---
title: "컴파일러 오류 C2760 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2760"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2760"
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2760
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류 : 'name1'이\(가\) 필요한데 'name2'을\(를\) 사용했습니다.  
  
 캐스팅 연산자가 잘못된 연산자와 함께 사용되었습니다.  
  
 다음 샘플에서는 C2760 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2760.cpp  
class B {};  
class D : public B {};  
  
void f(B* pb) {  
    D* pd1 = static_cast<D*>(pb);  
    D* pd2 = static_cast<D*>=(pb);  // C2760  
    D* pd3 = static_cast<D*=(pb);   // C2760  
}  
```