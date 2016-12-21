---
title: "컴파일러 오류 C2881 | Microsoft Docs"
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
  - "C2881"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2881"
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2881
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'namespace1' : 이미 'namespace2'의 별칭으로 사용되고 있습니다.  
  
 동일 이름을 두 네임스페이스에서 별칭으로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2881 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2881.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
namespace B {  
   int i;  
}  
  
namespace C = A;  
namespace C = B;   // C2881 C is already an alias for A  
```