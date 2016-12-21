---
title: "컴파일러 오류 C2165 | Microsoft Docs"
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
  - "C2165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2165"
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword': 데이터에 대한 포인터를 수정할 수 없습니다.  
  
 `__stdcall`, `__cdecl` 또는 `__fastcall` 키워드가 데이터에 대한 포인터를 수정하려고 시도합니다.  
  
 다음 샘플에서는 C2165를 생성합니다.  
  
```  
// C2165.cpp // compile with: /c char __cdecl *p;   // C2165 char *p;   // OK  
```