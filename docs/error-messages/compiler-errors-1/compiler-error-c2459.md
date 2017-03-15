---
title: "컴파일러 오류 C2459 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2459"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2459"
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2459
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 정의 중이므로 익명 멤버로서 추가할 수 없습니다.  
  
 클래스, 구조체 또는 공용 구조체가 자체 범위에서 익명 공용 구조체의 멤버에 의해 재정의되었습니다.  
  
 다음 샘플에서는 C2459 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2459.cpp  
// compile with: /c  
class C {  
   union { int C; };   // C2459  
   union { int D; };  
};  
```