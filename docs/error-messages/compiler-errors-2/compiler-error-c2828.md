---
title: "컴파일러 오류 C2828 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2828"
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이항 형식을 사용하여 'operator operator'을\(를\) 전역으로 재정의할 수 없습니다.  
  
 연산자가 개체의 외부에서 이항 형식을 사용할 수 없습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  오버로드된 연산자를 개체에 대해 지역적으로 만듭니다.  
  
2.  오버로드할 적절한 단항 연산자를 선택합니다.