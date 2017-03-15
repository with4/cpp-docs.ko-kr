---
title: "컴파일러 오류 C2724 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2724"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2724"
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2724
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'static'은 파일 범위에서 정의된 멤버 함수에 사용할 수 없습니다.  
  
 정적 멤버 함수는 외부 링크를 사용하여 선언해야 합니다.  
  
 다음 샘플에서는 C2724 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2724.cpp  
class C {  
   static void func();  
};  
  
static void C::func(){};   // C2724  
// try the following line instead  
// void C::func(){};  
```