---
title: "컴파일러 오류 C2480 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2480"
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'thread'는 정적 범위의 데이터 항목에만 유효합니다.  
  
 `thread` 특성은 자동 변수, 비정적 데이터 멤버, 함수 매개 변수와 함께 사용하거나 함수 선언 또는 정의에 대해 사용할 수 없습니다.  
  
 `thread` 특성은 전역 변수, 정적 데이터 멤버 및 지역 정적 변수에만 사용하십시오.  
  
 다음 샘플에서는 C2480 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```