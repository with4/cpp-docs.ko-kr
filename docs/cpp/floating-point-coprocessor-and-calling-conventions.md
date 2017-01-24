---
title: "부동 소수점 보조 프로세서 및 호출 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "부동 소수점 보조 프로세서"
  - "부동 소수점 숫자"
  - "부동 소수점 숫자, 보조 프로세서"
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 부동 소수점 보조 프로세서 및 호출 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

부동 소수점 보조 프로세서에 대한 어셈블리 루틴을 작성하는 경우 **float** 또는 **double** 값\(함수가 ST\(0\)에 반환해야 하는 값\)을 반환하지 않으면 부동 소수점 제어 단어를 유지하고 보조 프로세서 스택을 정리해야 합니다.  
  
## 참고 항목  
 [호출 규칙](../cpp/calling-conventions.md)