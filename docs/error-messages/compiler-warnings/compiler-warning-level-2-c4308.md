---
title: "컴파일러 경고 (수준 2) C4308 | Microsoft Docs"
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
  - "C4308"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4308"
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4308
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

음의 정수 계열 상수가 부호 없는 형식으로 변환되었습니다.  
  
 식에서 음의 정수 계열 상수를 부호 없는 형식으로 변환하므로  식의 결과 값은 의미가 없는 값입니다.  
  
## 예제  
  
```  
// C4308.cpp  
// compile with: /W2  
unsigned int u = (-5 + 3U);   // C4308  
  
int main()  
{  
}  
```