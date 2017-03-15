---
title: "이전 버전과의 호환성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이전 버전과의 호환성"
  - "이전 버전과의 호환성, C 런타임 라이브러리"
  - "호환성, C 런타임 라이브러리"
  - "CRT, 호환성"
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 이전 버전과의 호환성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제품 버전간의 호환성에 대해, 라이브러리 OLDNAMES.LIB는 새로운 이름으로 이전 이름들을 매핑합니다.  예를 들어, `open` `_open` 으로 매핑합니다.  다음 명령줄 옵션의 조합을 사용하여 컴파일 할때, OLDNAMES.LIB를 사용하여 명시적으로 연결해야 합니다.  
  
-   `/Zl` \(개체 파일에서 기본 라이브러리 이름을 생략\) 와 `/Ze` \(기본\-Microsoft 확장 사용\)  
  
-   `/link`\(링커\-컨트롤\), `/NOD` \(기본 라이브러리 검색 없음\), 와 `/Ze`  
  
 컴파일러 명령줄 옵션에 대한 자세한 내용은, [컴파일러 참조](../build/reference/compiler-options.md) 를 참고하세요.  
  
## 참고 항목  
 [호환성](../c-runtime-library/compatibility.md)