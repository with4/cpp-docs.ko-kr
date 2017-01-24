---
title: "컴파일러 경고 (수준 3) C4306 | Microsoft Docs"
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
  - "C4306"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4306"
ms.assetid: 5b2192d7-402d-4b6d-8619-08105e7dcac7
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4306
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***identifier* ' : '**   
 ***type1* '에서 더 큰 '**   
 ***type2* '\(으\)로의 변환입니다.**  
  
 식별자가 더 큰 포인터로의 형식 캐스트입니다.  이 경우 채워지지 않은 새 형식의 상위 비트가 0으로 채워집니다.  
  
 이 경고는 의도하지 않은 변환을 나타낼 수 있으며  결과 포인터를 사용할 수 없습니다.