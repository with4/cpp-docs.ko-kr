---
title: "컴파일러 오류 C2137 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2137"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2137"
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2137
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자 상수가 비어 있습니다.  
  
 빈 문자 상수\(' '\)는 허용되지 않습니다.  
  
 다음 샘플에서는 C2137을 생성합니다.  
  
```  
// C2137.cpp int main() { char c = '';   // C2137 char d = ' ';   // OK }  
```