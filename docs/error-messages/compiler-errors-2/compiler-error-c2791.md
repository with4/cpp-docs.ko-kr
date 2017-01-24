---
title: "컴파일러 오류 C2791 | Microsoft Docs"
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
  - "C2791"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2791"
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2791
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super'를 잘못 사용했습니다. 'class'에 기본 클래스가 없습니다.  
  
 [super](../../cpp/super.md) 키워드가 기본 클래스를 사용하지 않는 클래스 멤버 함수의 컨텍스트 내에서 사용되었습니다.  
  
 다음 샘플에서는 C2791 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```