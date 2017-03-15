---
title: "심각한 오류 C1055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1055"
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 심각한 오류 C1055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 키가 부족합니다.  
  
 소스 파일에 기호가 너무 많습니다.  컴파일러가 이 기호 테이블에 대한 해시 키를 다 써버렸습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  소스 파일을 좀 더 작은 여러 개의 파일로 분할합니다.  
  
2.  필요 없는 헤더 파일을 제거합니다.  
  
3.  새 변수를 만들지 않고 임시 및 전역 변수를 다시 사용합니다.