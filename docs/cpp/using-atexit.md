---
title: "atexit 사용 | Microsoft Docs"
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
  - "atexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atexit 함수"
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# atexit 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[atexit](../c-runtime-library/reference/atexit.md) 함수를 사용하여 프로그램 종료 전에 실행되는 종료 처리 함수를 지정할 수 있습니다.  `atexit`를 호출하기 전에 초기화된 전역 정적 개체는 종료 처리 함수의 실행 전에 소멸되지 않습니다.  
  
## 참고 항목  
 [추가 종료 고려 사항](../cpp/additional-termination-considerations.md)