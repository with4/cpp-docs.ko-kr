---
title: "컴파일러 오류 C2081 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2081"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2081"
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2081
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 정식 매개 변수 목록에 있는 이름이 잘못되었습니다.  
  
 식별자로 인해 구문 오류가 발생했습니다.  
  
 정식 매개 변수 목록에 이전 스타일을 사용한 경우 이 오류가 발생할 수 있습니다.  정식 매개 변수 목록에 정식 매개 변수의 형식을 지정해야 합니다.  
  
 다음 샘플에서는 C2081 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```