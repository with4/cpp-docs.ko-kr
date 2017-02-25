---
title: "컴파일러 오류 C2818 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2818"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2818"
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2818
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오버로드된 'operator \-\>''는 'type' 형식을 통해 재귀적으로 적용됩니다.  
  
 클래스 멤버 액세스 연산자의 재정의에는 재귀적 `return` 문이 포함됩니다.  재귀를 사용하여 `->` 연산자를 다시 정의하려면 재귀 루틴을 연산자 재정의 함수에서 호출되는 별개의 함수로 이동해야 합니다.