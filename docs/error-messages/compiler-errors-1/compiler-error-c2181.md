---
title: "컴파일러 오류 C2181 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2181"
ms.assetid: d52b2fe4-566a-40a9-b8e2-8dce1f287668
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

if와 짝을 이루지 않는 잘못된 else문입니다.  
  
 각 `else`에는 해당하는 `if`가 있어야 합니다.  
  
 다음 샘플에서는 C2181을 생성합니다.  
  
```  
// C2181.cpp int main() { int i = 0; else   // C2181 i = 1; }  
```  
  
 해결 방법:  
  
```  
// C2181b.cpp int main() { int i = 0; if(i) i = 0; else i = 1; }  
```