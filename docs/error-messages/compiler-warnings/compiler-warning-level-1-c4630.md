---
title: "컴파일러 경고 (수준 1) C4630 | Microsoft Docs"
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
  - "C4630"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4630"
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4630
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 멤버 정의에는 'extern' 저장소 클래스 지정자를 사용할 수 없습니다.  
  
 데이터 멤버 또는 멤버 함수를 `extern`으로 정의했습니다.  전체 개체가 외부 개체가 될 수 있더라도 멤버는 외부 멤버가 될 수 없습니다.  컴파일러에서 `extern` 키워드를 무시합니다.  다음 샘플에서는 C4630 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4630.cpp  
// compile with: /W1 /LD  
class A {  
   void func();  
};  
  
extern void A::func() {   // C4630, remove 'extern' to resolve  
}  
```