---
title: "식 계산기 오류 CXX0019 | Microsoft Docs"
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
  - "CXX0019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0019"
  - "CXX0019"
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 식 계산기 오류 CXX0019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 변환이 잘못되었습니다.  
  
 C 식 계산기가 작성된 대로 형식 변환을 수행할 수 없습니다.  
  
 이 오류는 CAN0019와 동일합니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  지정한 형식을 알 수 없습니다.  
  
2.  포인터 형식의 수준이 너무 많습니다.  예를 들면 다음과 같습니다.  
  
    ```  
    (char **)h_message  
    ```  
  
     위 형식 변환은 C 식 계산기가 계산할 수 없습니다.