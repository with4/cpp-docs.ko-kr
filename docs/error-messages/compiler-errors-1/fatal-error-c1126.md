---
title: "심각한 오류 C1126 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1126"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1126"
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 심각한 오류 C1126
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 자동 할당이 size을\(를\) 초과합니다.  
  
 함수의 지역 변수에 할당된 공간\+컴파일러가 사용하는 제한된 공간\(예: 스왑 가능 함수에 대해 추가 20바이트\)이 한계를 초과합니다.  
  
 이 오류를 해결하려면 `malloc` 또는 `new`를 사용하여 데이터 양을 더 많이 할당하십시오.