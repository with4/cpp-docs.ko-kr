---
title: "컴파일러 오류 C3106 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3106"
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': 명명되지 않은 인수는 명명된 인수의 앞에 와야 합니다.  
  
 명명되지 않은 인수는 명명된 인수보다 먼저 특성에 전달해야 합니다.  
  
 자세한 내용은 [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3106 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3106.cpp  
// compile with: /c  
[module(name="MyLib", dll)];   // C3106  
[module(dll, name="MyLib")];   // OK  
```