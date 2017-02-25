---
title: "블록 범위가 있는 이름의 링크 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "블록 범위[C++]"
  - "외부 링크, 범위 링크 규칙"
  - "링크[C++], 범위 링크 규칙"
  - "이름[C++], 범위 링크 규칙"
  - "범위[C++], 링크 규칙"
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 블록 범위가 있는 이름의 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 링크 규칙이 블록 범위가 있는 이름\(로컬 이름\)에 적용됩니다.  
  
-   `extern`으로 선언된 이름은 이전에 **정적**으로 선언된 경우가 아니면 외부 링크를 가지고 있습니다.  
  
-   블록 범위가 있는 다른 모든 이름에는 링크가 없습니다.  
  
## 참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)