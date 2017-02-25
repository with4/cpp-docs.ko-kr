---
title: "컴파일러 오류 C2593 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2593"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2593"
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2593
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator identifier'은\(는\) 모호합니다.  
  
 오버로드된 연산자에 대해 둘 이상의 연산자가 정의되었습니다.  
  
 이 오류는 하나 이상의 실제 매개 변수에 대한 명시적 캐스트를 사용하여 해결할 수 있습니다.  
  
 다음 샘플에서는 C2593 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2593.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
void operator+( X, X );  
void operator+( A, B );  
D d;  
  
int main() {  
   d +  d;         // C2593, D has an A, B, and X   
   (X)d + (X)d;    // OK, uses operator+( X, X )  
}  
```  
  
 이 오류는 `CArchive` 개체를 사용하여 부동 소수점 변수를 serialize하는 경우에 발생할 수 있습니다.  컴파일러가 `<<` 연산자를 모호한 것으로 식별합니다.  `CArchive`로 serialize할 수 있는 기본 C\+\+ 형식은 크기가 고정된 `BYTE`, `WORD`, `DWORD` 및 `LONG` 형식뿐입니다.  정수 계열 형식을 serialize하려면 이를 이러한 형식 중 하나로 캐스팅해야 합니다.  `CArchive::Write()` 멤버 함수를 사용하여 부동 소수점 형식을 보관해야 합니다.  
  
 다음 예제는 `ar`를 보관하기 위해 부동 소수점 변수\(`f`\)를 보관하는 방법을 보여 줍니다.  
  
```  
ar.Write(&f, sizeof( float ));  
```