---
title: "심각한 오류 C1009 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1009"
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 심각한 오류 C1009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 매크로가 너무 많이 중첩되었습니다.  
  
 컴파일러가 동시에 너무 많은 매크로를 확장하려고 했습니다.  컴파일러의 중첩 매크로 수준 한계는 256입니다.  중첩 매크로를 보다 간단한 매크로로 분할하십시오.