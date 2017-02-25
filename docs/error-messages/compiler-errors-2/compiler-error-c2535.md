---
title: "컴파일러 오류 C2535 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2535"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2535"
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2535
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 멤버 함수를 이미 정의했거나 선언했습니다.  
  
 이 오류는 오버로드된 함수에 대한 둘 이상의 정의 또는 선언에서 동일한 정식 매개 변수 목록을 사용하는 경우에 발생할 수 있습니다.  
  
 Dispose 함수로 인해 C2535 오류가 발생하는 경우 자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)를 참조하십시오.  
  
 ATL 프로젝트를 컴파일하는 경우에는 기술 자료 문서 Q241852를 참조하십시오.  
  
 다음 샘플에서는 C2535 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```