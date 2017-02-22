---
title: "컴파일러 오류 C3896 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3896"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3896"
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3896
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 잘못된 이니셜라이저: 이 리터럴 데이터 멤버는 'nullptr'로만 초기화할 수 있습니다.  
  
 [literal](../../windows/literal-cpp-component-extensions.md) 데이터 멤버를 잘못 초기화했습니다.  자세한 내용은 [nullptr](../../windows/nullptr-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3896 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```