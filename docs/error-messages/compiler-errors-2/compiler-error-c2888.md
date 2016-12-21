---
title: "컴파일러 오류 C2888 | Microsoft Docs"
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
  - "C2888"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2888"
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2888
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'namespace' 네임스페이스 안에서 기호를 정의할 수 없습니다.  
  
 네임스페이스 A에 속하는 기호는 A를 포함하는 네임스페이스에서 정의해야 합니다.  
  
 다음 샘플에서는 C2888 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2888.cpp  
// compile with: /c  
namespace M {  
   namespace N {  
      void f1();  
      void f2();  
   }  
  
   void N::f1() {}   // OK: namspace M encloses N  
}  
  
namespace O {  
   void M::N::f2() {}   // C2888 namespace O does not enclose M  
}  
```