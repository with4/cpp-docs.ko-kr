---
title: "컴파일러 경고 (수준 4) C4516 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4516"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4516"
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4516
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::symbol' : 액세스 선언은 사용되지 않습니다. 멤버 using 선언을 대신 사용하는 것이 좋습니다.  
  
 ANSI C\+\+ 위원회에서는 [using](../../cpp/using-declaration.md) 키워드 없이 파생 클래스의 멤버 액세스를 변경하는 액세스 선언이 오래된 방식이라고 발표했습니다.  따라서 액세스 선언이 이후 버전의 C\+\+에서 지원되지 않을 수 있습니다.  
  
 다음 샘플에서는 C4516 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```