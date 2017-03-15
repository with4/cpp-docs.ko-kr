---
title: "컴파일러 오류 C3292 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3292"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3292"
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3292
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cli 네임스페이스를 다시 열 수 없습니다.  
  
 cli 네임스페이스를 코드에서 선언할 수 없습니다.  자세한 내용은 [Platform, default, and cli Namespaces](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3292를 생성합니다.  
  
```  
// C3292.cpp // compile with: /clr /c namespace cli {};   // C3292  
```