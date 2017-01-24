---
title: "컴파일러 오류 C2702 | Microsoft Docs"
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
  - "C2702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2702"
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_except는 종료 블록에 나올 수 없습니다.  
  
 예외 처리기\(`__try`\/`__except`\)는 `__finally` 블록 내부에 중첩될 수 없습니다.  
  
 다음 샘플에서는 C2702 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2702.cpp  
// processor: x86 IPF  
int Counter;  
int main() {  
   __try {}  
   __finally {  
      __try {}   // C2702  
      __except( Counter ) {}   // C2702  
   }  
}  
```