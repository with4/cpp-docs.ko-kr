---
title: "컴파일러 오류 C2083 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2083"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2083"
ms.assetid: 5fc4f931-eab6-4d8d-a3ee-3b8e11e64b18
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2083
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

struct\/union 비교가 잘못되었습니다.  
  
 구조체 또는 공용 구조체는 다른 사용자 정의 형식과 직접 비교됩니다. 이는 비교 연산자를 정의했거나 스칼라 형식에 대한 변환이 존재하지 않는 한 허용되지 않습니다.