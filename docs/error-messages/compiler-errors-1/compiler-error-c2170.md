---
title: "컴파일러 오류 C2170 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2170"
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 함수로 선언하지 않았으므로 내장 함수일 수 없습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  `intrinsic` Pragma를 함수가 아닌 항목에 사용했습니다.  
  
2.  `intrinsic` Pragma를 내장 형식이 없는 함수에 사용했습니다.