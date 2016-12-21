---
title: "컴파일러 오류 C2063 | Microsoft Docs"
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
  - "C2063"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2063"
ms.assetid: 0a90c18f-4029-416a-9128-e8713b53e6f1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2063
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 함수가 아닙니다.  
  
 식별자가 함수로 사용되었지만 함수로 선언되지 않았습니다.  
  
 다음 샘플에서는 C2063을 생성합니다.  
  
```  
// C2063.c int main() { int i, j; j = i();    // C2063, i is not a function }  
```  
  
 해결 방법:  
  
```  
// C2063b.c int i() { return 0;} int main() { int j; j = i(); }  
```