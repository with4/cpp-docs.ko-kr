---
title: "embedded_idl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "embedded_idl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "embedded_idl 특성"
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# embedded_idl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 특성에서 생성된 코드를 유지한 상태에서 형식 라이브러리가 .tlh 파일에 작성되도록 지정합니다.  
  
## 구문  
  
```  
embedded_idl[("param")]  
```  
  
#### 매개 변수  
 `param`  
 다음 두 값 중 하나일 수 있습니다.  
  
-   emitidl: typelib에서 가져온 형식 정보가 특성 사용 프로젝트에 대해 생성된 IDL에 존재합니다.  `embedded_idl`에 대한 매개 변수를 지정하지 않는 경우 이 값이 기본값으로 적용됩니다.  
  
-   no\_emitidl: typelib에서 가져온 형식 정보가 특성 사용 프로젝트에 대해 생성된 IDL에 존재하지 않습니다.  
  
## 예제  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## 설명  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)