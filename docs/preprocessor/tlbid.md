---
title: "tlbid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tlbid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tlbid 특성"
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# tlbid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 기본 형식 라이브러리 이외의 라이브러리를 로드할 수 있도록 합니다.  
  
## 구문  
  
```  
tlbid(number)  
```  
  
#### 매개 변수  
 `number`  
 `filename`에 있는 형식 라이브러리의 수입니다.  
  
## 설명  
 다중 형식 라이브러리가 단일 DLL에 빌드된 경우 `tlbid`를 사용하여 기본 형식 라이브러리 이외의 라이브러리를 로드할 수 있습니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 다음과 동일합니다.  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)