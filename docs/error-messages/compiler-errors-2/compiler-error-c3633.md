---
title: "컴파일러 오류 C3633 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3633"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3633"
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# 컴파일러 오류 C3633
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member'을\(를\) 관리되는 'type'의 멤버로 정의할 수 없습니다.  
  
 CLR 참조 클래스 데이터 멤버는 POD가 아닌 C\+\+ 형식이 될 수 없습니다.  POD 네이티브 형식은 CLR 형식에서만 인스턴스화할 수 있습니다.  예를 들어 POD 형식은 복사 생성자나 할당 연산자를 포함할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3633 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  
  
## 예제  
 다음 샘플에서는 C3633 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3633_b.cpp  
// compile with: /clr:oldSyntax /c  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
__gc class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```