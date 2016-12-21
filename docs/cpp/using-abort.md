---
title: "abort 사용 | Microsoft Docs"
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
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort 함수"
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# abort 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[abort](../c-runtime-library/reference/abort.md) 함수를 호출하면 즉시 종료됩니다.  이 함수는 초기화된 전역 정적 개체에 대한 일반적인 소멸 프로세스를 건너뜁니다.  또한 이 함수는 `atexit` 함수를 사용하여 지정된 모든 특수 처리를 건너뜁니다.  
  
## 참고 항목  
 [추가 종료 고려 사항](../cpp/additional-termination-considerations.md)