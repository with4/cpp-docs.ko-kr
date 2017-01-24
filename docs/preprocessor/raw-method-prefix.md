---
title: "raw_method_prefix | Microsoft Docs"
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
  - "raw_method_prefix"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_method_prefix 특성"
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 이름 충돌을 방지하기 위해 다른 접두사를 지정합니다.  
  
## 구문  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### 매개 변수  
 `Prefix`  
 사용할 접두사입니다.  
  
## 설명  
 하위 수준 속성 및 메서드는 상위 수준 오류 처리 멤버 함수와의 이름 충돌을 방지하기 위해 **raw\_**라는 기본 접두사로 이름이 지정된 멤버 함수에 의해 노출됩니다.  
  
> [!NOTE]
>  `raw_method_prefix` 특성의 효과는 [raw\_interfaces\_only](#_predir_raw_interfaces_only) 특성의 존재에 의해 변경되지 않습니다.  접두사를 지정할 때 항상 `raw_method_prefix`가 `raw_interfaces_only`에 우선합니다.  두 특성 모두 동일한 `#import` 문에서 사용되는 경우 `raw_method_prefix` 특성에 의해 지정된 접두사가 사용됩니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)