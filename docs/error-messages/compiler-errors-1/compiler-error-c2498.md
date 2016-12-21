---
title: "컴파일러 오류 C2498 | Microsoft Docs"
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
  - "C2498"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2498"
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2498
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 'novtable'은 클래스 선언 또는 정의에만 적용할 수 있습니다.  
  
 이 오류는 함수와 함께 `__declspec(novtable)`을 사용하는 경우에 발생할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C2498 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```