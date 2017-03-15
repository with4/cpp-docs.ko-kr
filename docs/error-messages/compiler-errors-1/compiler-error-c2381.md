---
title: "컴파일러 오류 C2381 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2381"
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 재정의. \_\_declspec\(noreturn\)이 다릅니다.  
  
 함수가 선언된 다음 정의되었으나 정의에 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자가 사용되었습니다.  `noreturn`을 사용하면 함수가 재정의됩니다. 선언 및 정의에서의 `noreturn` 사용에 동의해야 합니다.  
  
 다음 샘플에서는 C2381 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```