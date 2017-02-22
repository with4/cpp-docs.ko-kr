---
title: "컴파일러 경고 C4867 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4867"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4867"
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# 컴파일러 경고 C4867
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 함수 호출에 인수 목록이 없습니다. 'call'을\(를\) 사용하여 멤버에 대한 포인터를 만드십시오.  
  
 멤버 함수를 가리키는 포인터가 잘못 초기화되었습니다.  
  
 이 경고는 Visual C\+\+ 2005에 대해 적용되었으며, 향상된 멤버 포인터 준수라는 컴파일러 규칙의 결과로 발생할 수 있습니다.  Visual C\+\+ 2005 이전에는 정상적으로 컴파일되던 코드도 이제 C4867을 발생시킬 수 있습니다.  
  
 이 경고는 항상 오류로서 발생합니다.  이 경고를 비활성화하려면 [경고](../../preprocessor/warning.md) pragma를 사용하십시오.  C4867 및 MFC\/ATL에 대한 자세한 내용은 [\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4867 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```