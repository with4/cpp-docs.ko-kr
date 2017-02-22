---
title: "implementation_only | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "implementation_only"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "implementation_only 특성"
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# implementation_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 .tlh 헤더 파일\(기본 헤더 파일\)을 생성하지 않습니다.  
  
## 구문  
  
```  
implementation_only  
```  
  
## 설명  
 이 파일에는 형식 라이브러리 내용을 노출하는 데 사용되는 모든 선언이 포함되어 있습니다.  .tli 헤더 파일이 래퍼 멤버 함수의 구현과 함께 생성되어 컴파일에 포함됩니다.  
  
 이 특성이 지정되면 .tli 헤더의 내용이 .tlh 헤더에서 일반적으로 사용되는 동일한 네임스페이스에 있습니다.  또한 멤버 함수가 인라인으로 선언되지 않습니다.  
  
 `implementation_only` 특성은 PCH\(미리 컴파일된 헤더\) 파일 외부에 구현을 유지하는 수단으로 [no\_implementation](../preprocessor/no-implementation.md) 특성과 함께 사용하기 위한 것입니다.  `no_implementation` 특성이 포함된 `#import` 문은 PCH를 만드는 데 사용되는 소스 영역에 배치됩니다.  생성된 PCH는 많은 소스 파일에서 사용됩니다.  이 경우 `implementation_only` 특성이 포함된 `#import` 문은 PCH 영역 외부에서 사용됩니다.  소스 파일 중 하나에서 한 번만 이 문을 사용해야 합니다.  이 문을 사용하면 각 소스 파일을 추가로 다시 컴파일할 필요 없이 필요한 래퍼 멤버 함수가 모두 생성됩니다.  
  
> [!NOTE]
>  한 `#import` 문의 `implementation_only` 특성은 `no_implementation` 특성이 포함된 동일한 형식 라이브러리의 다른 `#import` 문과 함께 사용해야 합니다.  이렇게 하지 않으면 컴파일러 오류가 생성됩니다.  그 이유는 `no_implementation` 특성이 포함된 `#import` 문에서 생성된 래퍼 클래스 정의가 `implementation_only` 특성으로 생성된 구현을 컴파일하는 데 필요하기 때문입니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)