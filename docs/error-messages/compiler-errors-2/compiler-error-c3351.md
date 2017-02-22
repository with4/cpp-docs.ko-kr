---
title: "컴파일러 오류 C3351 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3351"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3351"
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3351
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'object': 대리자 생성자: 두 번째 인수는 정적 멤버 함수 또는 전역 함수의 주소여야 합니다.  
  
 컴파일러에서 [정적](../../misc/static-cpp.md)으로 선언된 함수의 주소가 필요합니다.  
  
 다음 샘플에서는 C3351을 생성합니다.  
  
```  
// C3351a.cpp // compile with: /clr delegate int D(int, int); ref class C { public: int mf(int, int) { return 1; } static int mf2(int, int) { return 1; } }; int main() { System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351 System::Delegate ^pD2 = gcnew D(&C::mf2); }  
```  
  
 다음 샘플에서는 C3351을 생성합니다.  
  
```  
// C3351b.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __delegate int D(int, int); __gc class C { public: int mf(int, int) { // declare the function as static // static int mf(int, int) { return 1; } }; int main() { C *pC = new C; System::Delegate *pD = new D(0, &C::mf);   // C3351 }  
```