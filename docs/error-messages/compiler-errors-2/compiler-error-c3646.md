---
title: "컴파일러 오류 C3646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3646"
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier' : 알 수 없는 재정의 지정자입니다.  
  
 재정의 지정자가 필요한 위치에서 토큰을 발견했지만 이 토큰을 컴파일러가 인식할 수 없습니다.  
  
 자세한 내용은 [Override 지정자](../../windows/override-specifiers-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3646 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```