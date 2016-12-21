---
title: "컴파일러 경고 (수준 3) C4359 | Microsoft Docs"
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
  - "C4359"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4359"
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4359
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 실제 맞춤\(8\)이 \_\_declspec\(align\(\)\)에 지정된 값보다 큽니다.  
  
 형식에 대해 지정된 맞춤이 해당 데이터 멤버 중 하나의 형식 맞춤보다 작습니다.  자세한 내용은 [맞춤](../../cpp/align-cpp.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4359 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4359.cpp  
// compile with: /W3 /c  
struct __declspec(align(8)) C8 { __int64 i; };  
struct __declspec(align(4)) C4  { C8 m8; };   // C4359  
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK  
struct __declspec(align(16)) C16  { C8 m8; };   // OK  
```