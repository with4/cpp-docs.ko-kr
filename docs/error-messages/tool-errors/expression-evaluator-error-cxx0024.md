---
title: "식 계산기 오류 CXX0024 | Microsoft Docs"
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
  - "CXX0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0024"
  - "CXX0024"
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 식 계산기 오류 CXX0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

연산에 l\-value가 필요합니다.  
  
 l\-value가 필요한 연산에 l\-value로 계산되지 않는 식이 지정되었습니다.  
  
 l\-value\(할당문의 왼쪽에 나타나기 때문에 이렇게 부름\)는 메모리 위치를 참조하는 식입니다.  
  
 예를 들어, `buffer[count]`는 특정 메모리 위치를 가리키기 때문에 유효한 l\-value입니다.  논리 비교 `zed != 0`은 메모리 주소가 아닌 TRUE 또는 FALSE로 계산되기 때문에 유효한 l\-value가 아닙니다.  
  
 이 오류는 CAN0024와 동일합니다.