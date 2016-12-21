---
title: "컴파일러 오류 C3417 | Microsoft Docs"
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
  - "C3417"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3417"
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3417
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 값 형식은 사용자 정의 특수 멤버 함수를 포함할 수 없습니다.  
  
 값 형식은 기본 인스턴스 생성자, 소멸자 또는 복사 생성자 같은 함수를 포함할 수 없습니다.  
  
 다음 샘플에서는 C3517 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```