---
title: "컴파일러 오류 C2027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2027"
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정의되지 않은 형식 'type'을\(를\) 사용했습니다.  
  
 정의된 형식만 사용할 수 있습니다.  이 오류를 해결하려면 이 형식을 참조하기 전에 완전하게 정의해야 합니다.  
  
## 예제  
 다음 샘플에서는 C2027 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## 예제  
 선언되었으나 정의되지는 않은 형식에 대한 포인터를 선언할 수 있습니다.  그러나 Visual C\+\+에서는 정의되지 않은 형식에 대한 참조를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2027 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```