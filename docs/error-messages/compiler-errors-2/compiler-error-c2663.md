---
title: "컴파일러 오류 C2663 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2663"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2663"
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2663
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': number개의 오버로드에 'this' 포인터에 대한 올바른 변환이 없습니다.  
  
 컴파일러가 `this`를 오버로드된 멤버 함수 버전으로 변환하지 못했습니다.  
  
 이 오류는 `const`가 아닌 멤버 함수를 `const` 개체에 대해 호출하는 경우에 발생할 수 있습니다.  다음과 같이 해결할 수 있습니다.  
  
1.  개체 선언에서 `const`를 제거합니다.  
  
2.  멤버 함수 오버로드 중 하나에 `const`를 추가합니다.  
  
 다음 샘플에서는 C2663 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```