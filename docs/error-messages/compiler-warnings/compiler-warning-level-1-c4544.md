---
title: "컴파일러 경고 (수준 1) C4544 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4544"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4544"
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4544
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration': 이 템플릿 선언에서 기본 템플릿 인수가 무시되었습니다.  
  
 기본 템플릿 인수가 잘못된 위치에 지정되어 무시되었습니다.  클래스 템플릿의 기본 템플릿 인수는 클래스 템플릿의 선언이나 정의에만 지정할 수 있으며 클래스 템플릿의 멤버에는 지정할 수 없습니다.  
  
 이 샘플에서는 C4545를 생성하고 다음 샘플에서는 해결 방법을 보여 줍니다.  
  
```  
// C4544.cpp  
// compile with: /W1 /LD  
template <class T>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T=int>  
template <class T1>  
struct S<T>::S1 {};   // C4544  
```  
  
 이 예제에서는 기본 매개 변수가 클래스 템플릿`S`에 적용됩니다.  
  
```  
// C4544b.cpp  
// compile with: /LD  
template <class T = int>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T>  
template <class T1>  
struct S<T>::S1 {};  
```