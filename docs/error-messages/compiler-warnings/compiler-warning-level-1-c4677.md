---
title: "컴파일러 경고 (수준 1) C4677 | Microsoft Docs"
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
  - "C4677"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4677"
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4677
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 비전용 멤버의 시그니처에 어셈블리 전용 형식 'private\_type'이\(가\) 들어 있습니다.  
  
 어셈블리 외부에서 공용으로 액세스할 수 있는 형식에 전용으로만 액세스할 수 있는 형식을 사용했습니다.  공용 어셈블리 형식을 참조하는 구성 요소는 어셈블리 private 형식을 참조하는 멤버나 형식 멤버를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C4677 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4677.cpp  
// compile with: /clr /c /W1  
delegate void TestDel();  
public delegate void TestDel2();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;   // C4677  
   static event TestDel2^ MyClass_Event2;   // OK  
};  
```