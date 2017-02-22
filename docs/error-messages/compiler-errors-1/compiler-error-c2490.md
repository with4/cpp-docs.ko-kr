---
title: "컴파일러 오류 C2490 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2490"
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'naked' 특성이 있는 함수에서 'keyword'을\(를\) 사용할 수 없습니다.  
  
 [naked](../../cpp/naked-cpp.md)로 정의된 함수는 구조적 예외 처리를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2490 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2490.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   __try{}   // C2490, structured exception handling  
}  
```