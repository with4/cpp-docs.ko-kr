---
title: "컴파일러 오류 C3075 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3075 "
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'instance': 참조 형식 'type'의 인스턴스는 값 형식에 포함할 수 없습니다.  
  
 값 형식이 참조 형식의 인스턴스를 포함할 수 없습니다.  
  
 자세한 내용은 [참조 형식에 대한 C\+\+ 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3075를 생성합니다.  
  
```  
// C3075.cpp // compile with: /clr /c ref struct U {}; value struct X { U y;   // C3075 }; ref struct Y { U y;   // OK };  
```