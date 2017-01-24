---
title: "네임스페이스 이름 변경 | Microsoft Docs"
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
  - "rename_namespace"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "rename_namespace 특성"
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 네임스페이스 이름 변경
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 형식 라이브러리의 콘텐츠가 들어있는 네임스페이스의 이름을 바꿉니다.  
  
## 구문  
  
```  
rename_namespace("NewName")  
```  
  
#### 매개 변수  
 `NewName`  
 네임스페이스의 새 이름입니다.  
  
## 설명  
 단일 인수인 *NewName*을 사용합니다. 이 인수는 네임스페이스의 새 이름을 지정합니다.  
  
 네임스페이스를 제거하려면 대신 [no\_namespace](../preprocessor/no-namespace.md) 특성을 사용합니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)