---
title: "컴파일러 오류 C3118 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3118"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3118"
ms.assetid: 40fbe681-8868-4cb2-a2b2-4db4449319a7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3118
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : 인터페이스가 가상 상속을 지원하지 않습니다.  
  
 인터페이스에서 가상으로 상속하려고 했습니다.  예를 들면 다음과 같습니다.  
  
```  
// C3118.cpp  
__interface I1 {  
};  
  
__interface I2 : virtual I1 {   // C3118  
};  
```  
  
 위와 같은 코드에서 이 오류가 발생합니다.