---
title: "식 계산기 오류 CXX0025 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0025"
  - "CXX0025"
ms.assetid: 3e2fb541-63b3-46ac-9f93-3dadb253bcf6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 식 계산기 오류 CXX0025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

연산자에 구조체\/공용 구조체가 필요합니다.  
  
 `struct` 또는 **union** 형식의 식을 사용하는 연산자가 `struct` 또는 **union**이 아닌 식에 적용되었습니다.  
  
 클래스, 구조체 또는 공용 구조체 변수의 구성 요소는 완전하게 정규화된 이름을 가져야 합니다.  구성 요소는 완전한 사양 없이 입력할 수 없습니다.  
  
 이 오류는 CAN0025와 동일합니다.