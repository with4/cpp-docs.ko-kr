---
title: "컴파일러 오류 C3152 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3152"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3152"
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3152
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'construct': 'keyword'은\(는\) 클래스, 구조체 또는 가상 멤버 함수에만 적용될 수 있습니다.  
  
 특정 키워드는 C\+\+ 클래스에만 적용될 수 있습니다.  
  
 다음 샘플에서는 C3152를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3152.cpp  
// compile with: /clr /c  
ref class C {  
   int (*pfn)() sealed;   // C3152  
   virtual int g() sealed;   // OK  
};  
```  
  
 다음 샘플에서는 C3152를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3152_2.cpp  
// compile with: /clr:oldSyntax /c  
__value __interface A {};   // C3152;  
__value class X {};   // OK  
```