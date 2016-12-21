---
title: "컴파일러 오류 C3204 | Microsoft Docs"
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
  - "C3204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3204"
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_alloca'는 catch 블록 내부에서 호출할 수 없습니다.  
  
 이 오류는 catch 블록 내에서 [\_alloca](../../c-runtime-library/reference/alloca.md) 호출을 사용하는 경우에 발생합니다.  
  
## 예제  
 다음 샘플에서는 C3204를 생성합니다.  
  
```  
// C3204.cpp // compile with: /EHsc #include <malloc.h> void ShowError(void) { try { } catch(...) { _alloca(1);   // C3204 } }  
```