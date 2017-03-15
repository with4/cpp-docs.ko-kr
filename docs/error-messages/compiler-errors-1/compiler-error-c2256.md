---
title: "컴파일러 오류 C2256 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2256"
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function'에 friend 지정자를 잘못 사용했습니다.  
  
 소멸자 또는 생성자를 [friend](../../cpp/friend-cpp.md)로 지정할 수 없습니다.  
  
 다음 샘플에서는 C2256 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2256.cpp  
// compile with: /c  
class C {  
public:  
   friend ~C();   // C2256  
   ~C();   // OK  
};  
```