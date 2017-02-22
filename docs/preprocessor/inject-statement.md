---
title: "inject_statement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inject_statement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inject_statement 특성"
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# inject_statement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 소스 텍스트로서 인수를 형식 라이브러리 헤더에 삽입합니다.  
  
## 구문  
  
```  
inject_statement("source_text")  
```  
  
#### 매개 변수  
 `source_text`  
 형식 라이브러리 헤더 파일에 삽입되는 소스 텍스트입니다.  
  
## 설명  
 헤더 파일의 형식 라이브러리 내용을 래핑하는 네임스페이스 선언의 시작 부분에 텍스트가 배치됩니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)