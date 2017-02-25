---
title: "컴파일러 오류 C2438 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2438"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2438"
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2438
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 생성자를 통해 정적 클래스 데이터를 초기화할 수 없습니다.  
  
 클래스의 정적 멤버를 초기화하는 데 생성자가 사용됩니다.  정적 멤버는 클래스 선언 외부의 정의에서 초기화해야 합니다.  
  
 다음 샘플에서는 C2438 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2438.cpp  
struct X {  
   X(int i) : j(i) {}   // C2438  
   static int j;  
};  
  
int X::j;  
  
int main() {  
   X::j = 1;  
}  
```