---
title: "컴파일러 오류 C2378 | Microsoft Docs"
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
  - "C2378"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2378"
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2378
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 재정의. 형식 정의를 사용하여 기호를 오버로드할 수 없습니다.  
  
 식별자가 `typedef`로 다시 정의되었습니다.  
  
 다음 샘플에서는 C2378을 생성합니다.  
  
```  
// C2378.cpp // compile with: /c int i; typedef int i;   // C2378 typedef int b;   // OK  
```