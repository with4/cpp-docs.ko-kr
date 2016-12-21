---
title: "단순 할당 (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "할당 연산자[C++], 소규모"
  - "데이터 형식 변환[C++], 단순 할당"
  - "등호"
  - "연산자[C], 단순 할당"
  - "단순 할당 연산자"
  - "형식 변환[C++], 단순 할당"
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 단순 할당 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단순 할당 연산자는 오른쪽 피연산자를 왼쪽 피연산자에 할당합니다.  오른쪽 피연산자의 값은 할당 식의 형식으로 변환되며 왼쪽 피연산자로 지정된 개체에 저장된 값을 대체합니다.  할당에 대한 변환 규칙이 적용됩니다\([할당 변환](../c-language/assignment-conversions.md) 참조\).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 이 예제에서 `y`의 값은 **double** 형식으로 변환되어 `x`에 할당됩니다.  
  
## 참고 항목  
 [C 할당 연산자](../c-language/c-assignment-operators.md)