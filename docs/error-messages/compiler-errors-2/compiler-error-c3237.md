---
title: "컴파일러 오류 C3237 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3237"
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'generic\_class': 제네릭 클래스는 사용자 지정 특성이 될 수 없습니다.  
  
 제네릭 클래스는 사용자 정의 특성이 될 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3237을 생성합니다.  
  
```  
// C3237.cpp // compile with: /clr /c // C3237 expected using namespace System; generic <class T> // Delete the following line to resolve. [attribute(AttributeTargets::All, AllowMultiple=true)] public ref class GR {};  
```