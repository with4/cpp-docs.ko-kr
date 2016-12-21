---
title: "컴파일러 오류 C2474 | Microsoft Docs"
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
  - "C2474"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2474"
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2474
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword': 인접한 세미콜론이 없습니다. 키워드거나 식별자일 수 있습니다.  
  
 컴파일러가 세미콜론을 찾아야 하며 사용자 의도를 확인할 수 없습니다. 이 오류를 해결하려면 세미콜론을 추가합니다.  
  
## 예제  
 다음 샘플에서는 C2474를 생성합니다.  
  
```  
// C2474.cpp // compile with: /clr /c ref class A { ref class B {} property int i;   // C2474 error }; // OK ref class B { ref class D {}; property int i; }; ref class E { ref class F {} property; int i; };  
```