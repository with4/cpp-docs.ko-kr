---
title: "심각한 오류 C1002 | Microsoft Docs"
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
  - "C1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1002"
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2번 패스에서 컴파일러의 힙 공간이 부족합니다.  
  
 프로그램에 기호가 너무 많거나 식이 너무 복잡하여 둘째 패스 중에 컴파일러가 동적 메모리 공간을 다 써버렸습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  소스 파일을 좀 더 작은 여러 개의 파일로 나눕니다.  
  
2.  식을 좀 더 작은 하위 식으로 구분합니다.  
  
3.  메모리를 사용하는 드라이버나 다른 프로그램을 제거합니다.