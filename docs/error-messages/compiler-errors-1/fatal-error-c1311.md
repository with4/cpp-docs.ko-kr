---
title: "심각한 오류 C1311 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1311"
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 심각한 오류 C1311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COFF 형식은 number바이트의 주소를 사용하여 'var'을\(를\) 정적으로 초기화할 수 없습니다.  
  
 컴파일할 때 해당 값이 알려지지 않은 주소는 해당 형식의 저장소가 4바이트보다 작은 변수에 정적으로 할당할 수 없습니다.  
  
 이 오류는 다른 부분에 있어서는 유효한 C\+\+ 코드에서 발생할 수 있습니다.  
  
 다음 코드 예제에서는 C1311이 발생할 수 있는 조건 하나를 보여 줍니다.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```