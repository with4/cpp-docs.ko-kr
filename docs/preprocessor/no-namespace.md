---
title: "no_namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_namespace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_namespace 특성"
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# no_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 컴파일러가 생성하지 않은 네임스페이스 이름을 지정합니다.  
  
## 구문  
  
```  
no_namespace  
```  
  
## 설명  
 `#import` 헤더 파일의 형식 라이브러리 콘텐츠는 일반적으로 네임스페이스에 정의됩니다.  네임스페이스 이름은 원본 IDL 파일의 **library** 문에 지정됩니다.  `no_namespace` 특성을 지정하면 컴파일러가 이 네임스페이스를 생성하지 않습니다.  
  
 다른 네임스페이스 이름을 사용하려는 경우에는 대신 [네임스페이스 이름 변경](../preprocessor/rename-namespace.md) 특성을 사용하십시오.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)