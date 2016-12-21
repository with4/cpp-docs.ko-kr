---
title: "컴파일러 오류 C3611 | Microsoft Docs"
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
  - "C3611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3611"
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 봉인 함수에는 순수 지정자를 사용할 수 없습니다.  
  
 봉인 함수를 잘못 선언했습니다.  자세한 내용은 [sealed](../../windows/sealed-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3611 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```