---
title: "심각한 오류 C1026 | Microsoft Docs"
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
  - "C1026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1026"
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파서 스택 오버플로입니다. 프로그램이 너무 복잡합니다.  
  
 프로그램을 구문 분석하는 데 필요한 공간으로 인해 컴파일러 스택 오버플로가 발생했습니다.  
  
 다음을 수행하여 식의 복잡성을 감소시키십시오.  
  
-   `for` 및 `switch` 문에서 중첩을 감소시킵니다.  좀 더 많이 중첩된 문을 별도 함수에 배치합니다.  
  
-   함수 호출 또는 쉼표 연산자를 호출하는 긴 식을 구분합니다.