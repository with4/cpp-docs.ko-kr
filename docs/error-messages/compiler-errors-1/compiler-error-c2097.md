---
title: "컴파일러 오류 C2097 | Microsoft Docs"
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
  - "C2097"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2097"
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2097
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

초기화가 잘못되었습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  비상수 값을 사용하여 변수 초기화  
  
2.  긴 주소를 사용하여 짧은 주소 초기화  
  
3.  **\/Za**를 사용하여 컴파일할 때 비상수 식을 사용하여 로컬 구조체, 공용 구조체 또는 배열 초기화  
  
4.  쉼표 연산자를 포함하는 식을 사용하여 초기화  
  
5.  상수나 기호가 아닌 식을 사용하여 초기화