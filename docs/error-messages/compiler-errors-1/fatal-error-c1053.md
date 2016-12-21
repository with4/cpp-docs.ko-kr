---
title: "심각한 오류 C1053 | Microsoft Docs"
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
  - "C1053"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1053"
ms.assetid: f50c1c6a-d9cc-42fa-984e-4e2e6e9cd1b1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1053
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<identifier\>' : 함수가 너무 큽니다.  
  
 함수가 너무 커서 컴파일할 수 없습니다.  
  
### 아래의 해결 방법 따라 수정합니다.  
  
1.  최적화 없이 컴파일을 시도합니다.  
  
2.  함수를 좀 더 작은 함수로 나눕니다.  
  
3.  인라인 함수에 대한 호출을 줄입니다.