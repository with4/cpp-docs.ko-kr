---
title: "컴파일러 오류 C2489 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2489"
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 초기화된 자동 변수 또는 레지스터 변수를 'naked' 함수의 함수 범위에서 사용할 수 없습니다.  
  
 자세한 내용은 [naked](../../cpp/naked-cpp.md)을 참조하십시오.  
  
 다음 샘플에서는 C2489 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2489.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   int i = 1;   // C2489  
   register int j = 1;   // C2489  
}  
```