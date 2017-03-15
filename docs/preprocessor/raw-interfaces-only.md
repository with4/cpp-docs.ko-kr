---
title: "raw_interfaces_only | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_interfaces_only"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_interfaces_only 특성"
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# raw_interfaces_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 오류 처리 래퍼 함수 및 해당 래퍼 함수를 사용하는 [속성](../cpp/property-cpp.md) 선언을 생성하지 않습니다.  
  
## 구문  
  
```  
raw_interfaces_only  
```  
  
## 설명  
 또한 `raw_interfaces_only` 특성을 사용하면 비속성 함수 명명에 사용된 기본 접두사가 제거됩니다.  대개 접두사는 **raw\_**입니다.  이 특성이 지정되면 형식 라이브러리에서 직접 함수 이름을 가져옵니다.  
  
 이 특성을 사용하면 형식 라이브러리의 하위 내용만 노출할 수 있습니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)