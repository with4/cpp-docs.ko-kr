---
title: "컴파일러 오류 C3452 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3452"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3452"
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3452
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

목록 인수 멤버가 상수가 아닙니다.  
  
 인수가 컴파일 시간에 계산할 수 있는 값인 상수가 필요한 특성에 전달되었습니다.  
  
## 예제  
 다음 샘플에서는 C3452를 생성합니다.  
  
```  
// C3452.cpp // compile with: /c int i; [module( name="mod", type=dll, custom={i} ) ];   // C3452 // try the following line instead // [module( name="mod", type=dll, custom={"a"} ) ];  
```