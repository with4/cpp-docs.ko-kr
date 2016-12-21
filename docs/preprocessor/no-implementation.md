---
title: "no_implementation | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_implementation"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_implementation 특성"
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_implementation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 래퍼 멤버 함수의 구현이 포함된 .tli 헤더를 생성하지 않습니다.  
  
## 구문  
  
```  
no_implementation  
```  
  
## 설명  
 이 특성이 지정된 경우 형식 라이브러리 항목을 노출하는 선언이 포함된 .tlh 헤더가 .tli 헤더 파일을 포함하는 `#include` 문 없이 생성됩니다.  
  
 이 특성은 [implementation\_only](../preprocessor/implementation-only.md)와 함께 사용됩니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)