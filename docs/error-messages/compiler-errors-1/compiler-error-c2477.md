---
title: "컴파일러 오류 C2477 | Microsoft Docs"
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
  - "C2477"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2477"
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2477
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 정적 데이터 멤버는 파생 클래스를 통해 초기화할 수 없습니다.  
  
 템플릿 클래스의 정적 데이터 멤버가 잘못 초기화되었습니다.  이는 ISO C\+\+ 표준과의 호환을 위해 Visual C\+\+ .NET 2003 이전 버전의 Visual C\+\+ 컴파일러에 이루어진 주요 변경 내용입니다.  
  
 다음 샘플에서는 C2477 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```