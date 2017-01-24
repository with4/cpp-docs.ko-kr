---
title: "컴파일러 경고(수준 1) C4182 | Microsoft Docs"
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
  - "C4182"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4182"
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4182
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#include 중첩 수준은 'number'입니다. 무한 재귀가 발생할 수 있습니다.  
  
 중첩된 포함 파일의 수로 인해 힙의 공간이 부족합니다. 다른 포함 파일에 포함된 포함 파일이 중첩됩니다.  
  
 이 메시지는 정보 제공을 위해 제공되며 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) 오류를 생성합니다.