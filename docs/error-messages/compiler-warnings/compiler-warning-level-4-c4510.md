---
title: "컴파일러 경고 (수준 4) C4510 | Microsoft Docs"
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
  - "C4510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4510"
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 기본 생성자를 생성하지 못했습니다.  
  
 컴파일러에서 지정된 클래스에 대한 기본 생성자를 생성하지 못했으며 사용자 정의 생성자도 만들어지지 않았습니다.  따라서 이 형식의 개체를 만들 수 없습니다.  
  
 컴파일러에서 기본 생성자를 생성하는 데 문제를 일으키는 원인은 다음과 같습니다.  
  
-   const 데이터 멤버  
  
-   참조인 데이터 멤버  
  
 이러한 멤버를 초기화하는 클래스에 대해 사용자 정의 기본 생성자를 만들어야 합니다.  
  
 다음 샘플에서는 C4510 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```