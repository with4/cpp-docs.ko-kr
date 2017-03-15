---
title: "high_property_prefixes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "high_property_prefixes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "high_property_prefixes 특성"
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# high_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 세 가지 속성 메서드의 대체 접두사를 지정합니다.  
  
## 구문  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### 매개 변수  
 `GetPrefix`  
 **propget** 메서드에 사용되는 접두사입니다.  
  
 `PutPrefix`  
 **propput** 메서드에 사용되는 접두사입니다.  
  
 `PutRefPrefix`  
 **propputref** 메서드에 사용되는 접두사입니다.  
  
## 설명  
 기본적으로 높은 수준의 오류 처리 **propget**, **propput** 및 **propputref** 메서드는 각각 **Get**, `Put` 및 **PutRef** 접두사로 명명된 멤버 함수에 의해 노출됩니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)