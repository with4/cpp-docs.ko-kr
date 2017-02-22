---
title: "컴파일러 오류 C2652 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2652"
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 복사 생성자가 잘못되었습니다. 첫째 매개 변수가 'identifier'이\(가\) 아니어야 합니다.  
  
 복사 생성자의 첫째 매개 변수 형식이 클래스, 구조체 또는 공용 구조체에 대해 정의된 형식과 같습니다.  첫째 매개 변수는 형식에 대한 참조일 수 있지만 형식 자체일 수는 없습니다.  
  
 다음 샘플에서는 C2651 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```