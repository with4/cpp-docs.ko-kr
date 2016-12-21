---
title: "컴파일러 오류 C2790 | Microsoft Docs"
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
  - "C2790"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2790"
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2790
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super' : 이 키워드는 클래스 멤버 함수의 본문 안에서만 사용할 수 있습니다.  
  
 이 오류 메시지는 사용자가 멤버 함수 컨텍스트 외부에서 [super](../../cpp/super.md) 키워드를 사용하려고 할 경우에 표시됩니다.  
  
 다음 샘플에서는 C2790 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```