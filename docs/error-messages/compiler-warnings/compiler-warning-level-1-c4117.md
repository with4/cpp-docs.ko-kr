---
title: "컴파일러 경고(수준 1) C4117 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4117"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4117"
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고(수준 1) C4117
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' 매크로 이름이 예약되었습니다. 'Command'는 무시됩니다.  
  
### 다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  미리 정의된 매크로를 정의 또는 정의 해제하려고 합니다.  
  
2.  **정의된** 전처리기 연산자를 정의 또는 정의 해제하려고 합니다.  
  
 다음 샘플에서는 C4117을 생성합니다.  
  
```  
// C4117.cpp // compile with: /W1 #define __FILE__ test         // C4117. __FILE__ is a predefined macro #define ValidMacroName test   // ok int main() { }  
```