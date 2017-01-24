---
title: "include() | Microsoft Docs"
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
  - "include()"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "include() 특성"
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# include()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 자동 제외를 사용하지 않도록 설정합니다.  
  
## 구문  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### 매개 변수  
 `Name1`  
 강제로 포함할 첫 번째 항목입니다.  
  
 `Name2`  
 필요할 경우 강제로 포함할 두 번째 항목입니다.  
  
## 설명  
 형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다.  `#import`는 다양한 정의 오류를 자동으로 제외하여 해당 오류를 방지하려고 합니다.  항목을 포함해야 하는데 [컴파일러 경고 \(수준 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)에 나온 대로 항목이 제외된 경우 이 특성을 사용하여 자동 제외를 사용하지 않게 설정할 수 있습니다.  이 특성은 각각 포함할 형식 라이브러리 항목의 이름이 될 인수 몇 개를 가질 수 있습니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)