---
title: "컴파일러 경고 (수준 1) C4230 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4230"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4230"
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4230
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오래된 구문을 사용했습니다. 한정자\(modifier\)\/한정자\(qualifier\)가 섞여 있습니다. 한정자\(qualifier\)가 무시됩니다.  
  
 한정자를 `__cdecl`과 같은 Microsoft 한정자 앞에 사용하는 것은 오래된 방법입니다.  
  
## 예제  
  
```  
// C4230.cpp  
// compile with: /W1 /LD  
int __cdecl const function1();   // C4230 const ignored  
```