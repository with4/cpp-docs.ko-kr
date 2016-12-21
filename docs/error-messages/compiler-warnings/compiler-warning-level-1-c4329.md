---
title: "컴파일러 경고 (수준 1) C4329 | Microsoft Docs"
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
  - "C4329"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4329"
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4329
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(align\(\)\)이 enum에서 무시됩니다.  
  
 `enum`에는 [\_\_declspec](../../cpp/declspec.md) 한정자의 [align](../../cpp/align-cpp.md) 키워드를 사용할 수 없습니다.  다음 샘플에서는 C4329 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4329.cpp  
// compile with: /W1 /LD  
enum __declspec(align(256)) TestEnum {   // C4329  
   TESTVAL1,  
   TESTVAL2,  
   TESTVAL3  
};  
__declspec(align(256)) enum TestEnum1;  
```