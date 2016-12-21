---
title: "컴파일러 오류 C2827 | Microsoft Docs"
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
  - "C2827"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2827"
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2827
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단항 형식을 사용하여 'operator operator'을\(를\) 전역으로 재정의할 수 없습니다.  
  
 연산자가 개체의 외부에서 단항 형식을 사용할 수 없습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  오버로드된 연산자를 개체에 대해 지역적으로 만듭니다.  
  
2.  오버로드할 적절한 단항 연산자를 선택합니다.