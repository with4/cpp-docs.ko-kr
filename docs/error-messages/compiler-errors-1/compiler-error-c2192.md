---
title: "컴파일러 오류 C2192 | Microsoft Docs"
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
  - "C2192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2192"
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매개 변수 'number' 선언이 다릅니다.  
  
 C 함수가 각기 다른 매개 변수 목록을 사용하여 두 번 선언되었습니다.  C는 오버로드된 함수를 지원하지 않습니다.  
  
 다음 샘플에서는 C2192 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2192.c  
// compile with: /Za /c  
void func( float, int );  
void func( int, float );   // C2192, different parameter list  
void func2( int, float );   // OK  
```