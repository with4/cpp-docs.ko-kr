---
title: "no_auto_exclude | Microsoft Docs"
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
  - "no_auto_exclude"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_auto_exclude 특성"
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_auto_exclude
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 자동 제외를 사용하지 않도록 설정합니다.  
  
## 구문  
  
```  
no_auto_exclude  
```  
  
## 설명  
 형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다.  `#import`는 다양한 정의 오류를 자동으로 제외하여 해당 오류를 방지하려고 합니다.  이 작업이 완료되면 제외된 각 항목에 대해 [컴파일러 경고 \(수준 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)가 발급됩니다.  이 특성을 사용하여 자동 제외를 사용하지 않도록 설정할 수 있습니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)