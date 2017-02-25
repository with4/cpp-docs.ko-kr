---
title: "raw_dispinterfaces | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_dispinterfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_dispinterfaces 특성"
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# raw_dispinterfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 **IDispatch::Invoke**를 호출하고 `HRESULT` 오류 코드를 반환하는 dispinterface 메서드 및 속성에 대해 하위 수준의 래퍼 함수를 생성하라고 컴파일러에 지시합니다.  
  
## 구문  
  
```  
raw_dispinterfaces  
```  
  
## 설명  
 이 특성이 지정되지 않은 경우 실패 시 C\+\+ 예외를 throw하는 상위 수준 래퍼만 생성됩니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)