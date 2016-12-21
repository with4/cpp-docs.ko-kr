---
title: "컴파일러 경고 (수준 1) C4441 | Microsoft Docs"
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
  - "C4441"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4441"
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4441
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cc1'의 호출 규칙이 무시되고 대신 'cc2'이\(가\) 사용됩니다.  
  
 관리되는 사용자 정의 형식 및 전역 함수 제네릭의 멤버 함수에서는 [\_\_clrcall](../../cpp/clrcall.md) 호출 규칙을 사용해야 합니다.  컴파일러에서 `__clrcall`을 사용합니다.  
  
## 예제  
 다음 샘플에서는 C4441 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4441.cpp  
// compile with: /clr /W1 /c  
generic <class ItemType>  
void __cdecl Test(ItemType item) {}   // C4441  
// try the following line instead  
// void Test(ItemType item) {}  
  
ref struct MyStruct {  
   void __cdecl Test(){}   // C4441  
   void Test2(){}   // OK  
};  
```