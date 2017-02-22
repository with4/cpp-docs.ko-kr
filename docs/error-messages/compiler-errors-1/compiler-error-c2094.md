---
title: "컴파일러 오류 C2094 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2094"
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' 레이블이 정의되지 않았습니다.  
  
 [goto](../Topic/goto%20\(C%23%20Reference\).md) 문에서 사용하는 레이블이 함수에 존재하지 않습니다.  
  
 다음 샘플에서는 C2094를 생성합니다.  
  
```  
// C2094.c int main() { goto test; }   // C2094  
```  
  
 해결 방법:  
  
```  
// C2094b.c int main() { goto test; test: { } }  
```