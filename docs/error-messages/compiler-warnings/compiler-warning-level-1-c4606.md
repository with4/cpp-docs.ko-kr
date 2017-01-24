---
title: "컴파일러 경고 (수준 1) C4606 | Microsoft Docs"
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
  - "C4606"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4606"
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4606
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma warning : 'warning\_number'이\(가\) 무시됩니다. 코드 분석 경고가 경고 수준과 연결되어 있지 않습니다.  
  
 코드 분석 경고와 관련하여 `error`, `once` 및 `default`만 [경고](../../preprocessor/warning.md) pragma에 지원됩니다.  
  
## 예제  
 다음 샘플에서는 C4606 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4606.cpp  
// compile with: /c /W1  
#pragma warning(1: 6001)   // C4606  
#pragma warning(once: 6001)   // OK  
```