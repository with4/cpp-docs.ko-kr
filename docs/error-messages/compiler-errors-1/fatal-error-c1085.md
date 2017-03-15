---
title: "심각한 오류 C1085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1085"
ms.assetid: f2766365-d09b-4299-8a98-12e5aca98568
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 심각한 오류 C1085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

filetype 파일에 쓸 수 없습니다. 'file': message  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  읽기 전용 드라이브입니다.  
  
2.  드라이브가 꽉 찼습니다.  
  
3.  공유 위반입니다.  
  
4.  "잘못된 파일 수"라는 메시지가 표시되는 경우 파일이 백그라운드에서 컴파일되는 동안 포그라운드에서 닫혔을 수도 있습니다.