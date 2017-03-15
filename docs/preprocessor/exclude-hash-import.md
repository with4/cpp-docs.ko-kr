---
title: "exclude (#import) | Microsoft Docs"
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
  - "exclude"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "exclude 특성"
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exclude (#import)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 생성되는 형식 라이브러리 헤더 파일에서 항목을 제외시킵니다.  
  
## 구문  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
#### 매개 변수  
 `Name1`  
 제외시킬 첫 번째 항목입니다.  
  
 `Name2`  
 필요할 경우 제외시킬 두 번째 항목입니다.  
  
## 설명  
 형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다.  이 특성은 여러 개의 인수를 가질 수 있으며, 최고 수준의 형식 라이브러리 항목은 제외됩니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)