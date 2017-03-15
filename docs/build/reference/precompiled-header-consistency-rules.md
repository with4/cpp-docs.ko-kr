---
title: "미리 컴파일된 헤더의 일관성 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "미리 컴파일된 헤더 파일, 일관성 규칙"
ms.assetid: 844b1a14-5b0b-4276-a1f5-cc62f13f6dda
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 미리 컴파일된 헤더의 일관성 규칙
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 단원에서는 미리 컴파일된 헤더를 보다 효율적으로 사용하도록 도와 주는 지침에 대해 설명합니다.  
  
-   [미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙](../../build/reference/consistency-rules-for-per-file-use-of-precompiled-headers.md)  
  
-   [\/Yc 및 \/Yu에 대한 일관성 규칙](../../build/reference/consistency-rules-for-yc-and-yu.md)  
  
 PCH 파일에는 프로그램에 대한 메모리 주소 정보뿐만 아니라 컴퓨터 환경에 대한 정보도 포함되어 있으므로 PCH 파일은 해당 파일을 만든 컴퓨터에서만 사용해야 합니다.  
  
## 참고 항목  
 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)