---
title: "컴파일러 오류 C2371 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2371"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2371"
ms.assetid: d383993d-05ef-4e35-8129-3b58a6f7b7b7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2371
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 재정의. 기본 형식이 다릅니다.  
  
 식별자가 이미 선언되었습니다.  
  
 다음 샘플에서는 C2371을 생성합니다.  
  
```  
// C2371.cpp int main() { int i; float i;   // C2371, redefinition float f;   // OK }  
```