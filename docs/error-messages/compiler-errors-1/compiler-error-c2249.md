---
title: "컴파일러 오류 C2249 | Microsoft Docs"
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
  - "C2249"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2249"
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2249
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 액세스 멤버\(가상 기본 'class'에서 선언한\)에 액세스할 수 있는 경로가 없습니다.  
  
 `member`가 비공용 `virtual` 기본 클래스 또는 구조체에서 상속되었습니다.  
  
## 예제  
 다음 샘플에서는 C2249 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2249.cpp  
class A {  
private:  
   void privFunc( void ) {};  
public:  
   void pubFunc( void ) {};  
};  
  
class B : virtual public A {} b;  
  
int main() {  
   b.privFunc();    // C2249, private member of A  
   b.pubFunc();    // OK  
}  
```  
  
## 예제  
 C2249는 표준 C\+\+ 라이브러리의 스트림을 다른 스트림에 할당하려는 경우에도 발생할 수 있습니다.  다음 샘플에서는 C2249 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2249_2.cpp  
#include <iostream>  
using namespace std;  
int main() {  
   cout = cerr;   // C2249  
   #define cout cerr;   // OK  
}  
```