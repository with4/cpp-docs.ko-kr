---
title: "raw_property_prefixes | Microsoft Docs"
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
  - "raw_property_prefixes"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_property_prefixes 특성"
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 세 가지 속성 메서드의 대체 접두사를 지정합니다.  
  
## 구문  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### 매개 변수  
 `GetPrefix`  
 **propget** 메서드에 사용되는 접두사입니다.  
  
 `PutPrefix`  
 **propput** 메서드에 사용되는 접두사입니다.  
  
 `PutRefPrefix`  
 **propputref** 메서드에 사용되는 접두사입니다.  
  
## 설명  
 기본적으로 하위 수준의 **propget**, **propput** 및 **propputref** 메서드는 각각 **get\_**, **put\_** 및 **putref\_**의 접두사로 명명된 멤버 함수에 의해 노출됩니다.  이 접두사는 MIDL로 생성한 헤더 파일에 사용되는 이름과 호환됩니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)