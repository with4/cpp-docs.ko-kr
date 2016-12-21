---
title: "no_registry | Microsoft Docs"
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
  - "no_registry"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_registry 특성"
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_registry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`no_registry`는 `#import`를 사용하여 가져온 형식 라이브러리를 레지스트리에서 검색하지 않도록 컴파일러에 지시합니다.  
  
## 구문  
  
```  
  
#import filename no_registry  
```  
  
#### 매개 변수  
 *filename*  
 형식 라이브러리입니다.  
  
## 설명  
 참조된 형식 라이브러리가 포함 디렉터에 없는 경우 형식 라이브러리가 레지스트리에 있는 경우에도 컴파일이 실패합니다. `no_registry`는 `auto_search`를 사용하여 암시적으로 가져온 다른 형식 라이브러리에 전파됩니다.  
  
 컴파일러는 파일 이름으로 지정되고 `#import`에 직접 전달된 형식 라이브러리를 레지스트리에서 검색하지 않습니다.  
  
 `auto_search`가 지정된 경우 추가 `#import`는 초기 `#import`의 `no_registry` 설정을 사용하여 생성됩니다. 초기 `#import` 지시문이 `no_registry`인 경우 `auto_search`를 통해 생성된 `#import`도 `no_registry`입니다.  
  
 `no_registry`는 컴파일러가 이전 버전의 파일을 레지스트리에서 찾을 위험 없이 상호 참조된 형식 라이브러리를 가져오려는 경우에 유용합니다. 형식 라이브러리가 등록되지 않는 경우에도 `no_registry`가 유용합니다.  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)