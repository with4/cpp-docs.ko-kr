---
title: "컴파일러 오류 C2491 | Microsoft Docs"
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
  - "C2491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2491"
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': dllimport 함수를 정의할 수 없습니다.  
  
 데이터, 정적 데이터 멤버 및 함수는 `dllimport`로 선언될 수는 있지만 `dllimport`로 정의되지는 않습니다.  
  
 이 문제를 해결하려면 함수 정의에서 `__declspec(dllimport)` 지정자를 제거합니다.  
  
 다음 샘플에서는 C2491 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```