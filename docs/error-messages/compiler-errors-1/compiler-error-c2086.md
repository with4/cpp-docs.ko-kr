---
title: "컴파일러 오류 C2086 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2086"
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 재정의  
  
 식별자가 두 번 이상 정의되었거나 다음 선언이 이전 선언과 다릅니다.  
  
 C2086은 참조된 C\# 어셈블리에 대한 증분 빌드의 결과로 발생할 수도 있습니다.  이 오류를 해결하려면 C\# 어셈블리를 다시 빌드해야 합니다.  
  
 다음 샘플에서는 C2086 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```