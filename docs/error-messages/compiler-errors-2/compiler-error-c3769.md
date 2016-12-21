---
title: "컴파일러 오류 C3769 | Microsoft Docs"
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
  - "C3769"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3769"
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3769
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 중첩된 클래스의 이름은 바로 바깥쪽의 클래스의 이름과 같으면 안 됩니다.  
  
 중첩된 클래스의 이름은 바로 바깥쪽 클래스의 이름과 같으면 안 됩니다.  
  
## 예제  
 다음 샘플에서는 C3769 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```