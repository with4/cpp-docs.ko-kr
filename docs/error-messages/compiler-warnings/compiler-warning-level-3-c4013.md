---
title: "컴파일러 경고 (수준 3) C4013 | Microsoft Docs"
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
  - "C4013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4013"
ms.assetid: 9f9afc71-6e78-463d-9d66-3012d6a3cd5d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function'이\(가\) 정의되지 않았습니다. extern은 int형을 반환하는 것으로 간주합니다.  
  
 컴파일러가 정의되지 않은 함수에 대한 호출을 발견했습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  함수 이름의 철자가 잘못되었습니다.  
  
2.  외부 함수가 `extern`으로 프로토타입화되지 않았습니다.