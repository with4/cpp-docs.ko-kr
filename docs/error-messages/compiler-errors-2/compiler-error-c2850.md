---
title: "컴파일러 오류 C2850 | Microsoft Docs"
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
  - "C2850"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2850"
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2850
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'construct' : 파일 범위에서만 사용할 수 있습니다. 중첩된 구문에는 사용할 수 없습니다.  
  
 생성자\(예: 일부 pragma\)는 전역 범위에만 표시될 수 있습니다.  
  
 다음 샘플에서는 C2850 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2850.cpp  
// compile with: /c /Yc  
// try the following line instead  
// #pragma hdrstop  
namespace X {  
   #pragma hdrstop   // C2850  
};  
```