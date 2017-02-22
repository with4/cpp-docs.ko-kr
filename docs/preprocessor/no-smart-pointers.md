---
title: "no_smart_pointers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_search_pointers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_smart_pointers 특성"
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# no_smart_pointers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 형식 라이브러리의 모든 인터페이스에 대한 스마트 포인터를 만들지 않습니다.  
  
## 구문  
  
```  
no_smart_pointers  
```  
  
## 설명  
 `#import`를 사용하는 경우 기본적으로 형식 라이브러리에 있는 모든 인터페이스에 대한 스마트 포인터 선언을 가져옵니다.  이러한 스마트 포인터는 [\_com\_ptr\_t 클래스](../cpp/com-ptr-t-class.md) 형식입니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)