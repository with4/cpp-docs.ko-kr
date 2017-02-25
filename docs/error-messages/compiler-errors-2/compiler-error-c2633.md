---
title: "컴파일러 오류 C2633 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2633"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2633"
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2633
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 생성자에 맞는 유일한 저장소 클래스는 'inline'입니다.  
  
 생성자가 inline 이외의 저장소 클래스로 선언되었습니다.  
  
 다음 샘플에서는 C2633 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2633.cpp  
// compile with: /c  
class C {  
   extern C();   // C2633, not inline  
   inline C();   // OK  
};  
```