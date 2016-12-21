---
title: "컴파일러 오류 C2990 | Microsoft Docs"
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
  - "C2990"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2990"
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2990
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 비클래스 'type'이\(가\) 이미 클래스 'type'\(으\)로 선언되었습니다.  
  
 비 제네릭 또는 템플릿 클래스가 제네릭 또는 템플릿 클래스를 다시 정의합니다.  헤더 파일의 충돌 여부를 확인하십시오.  
  
 다음 샘플에서는 C2990 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 제네릭을 사용하는 경우에도 C2990이 발생할 수 있습니다.  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 C2990은 Visual C\+\+ 2005용 Visual C\+\+ 컴파일러의 변경 내용으로 인해 발생할 수도 있습니다. 이제 컴파일러에서 동일한 형식에 대한 선언이 여러 개인 경우 템플릿 사양과 관련하여 각 선언이 모두 동일해야 합니다.  
  
 다음 샘플에서는 C2990 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```