---
title: "컴파일러 경고 (수준 3) C4723 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4723"
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 3) C4723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

0의 나누기 연산이 발생할 수 있습니다.  
  
 나누기 연산의 두 번째 연산자가 컴파일 타임에 0으로 계산되었으므로 정의되지 않은 결과가 발생합니다.  
  
 이 경고는 [\/Og](../../build/reference/og-global-optimizations.md) 또는 \/Og를 수반하는 최적화 옵션을 사용할 때에만 발생합니다.  
  
 컴파일러에서 0 피연산자를 생성했을 수도 있습니다.