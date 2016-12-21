---
title: "main 함수 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Main"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main 함수, 사용 시 적용되는 제한"
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# main 함수 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 모든 C\+\+ 함수에는 적용되지 않는 **main** 함수에 대한 제한이 몇 가지 있습니다.  **main** 함수에 대한 제한은 다음과 같습니다.  
  
-   오버로드될 수 없습니다\([오버로드](../misc/overloading-cpp.md) 참조\).  
  
-   **inline**으로 선언될 수 없습니다.  
  
-   **static**으로 선언될 수 없습니다.  
  
-   주소를 사용할 수 없습니다.  
  
-   호출할 수 없습니다.  
  
## 참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)