---
title: "컴파일러 오류 C3235 | Microsoft Docs"
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
  - "C3235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3235"
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specialization': 제네릭 클래스의 명시적 특수화 또는 부분 특수화는 허용되지 않습니다.  
  
 명시적 특수화 또는 부분 특수화에 제네릭 클래스를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3235를 생성합니다.  
  
```  
// C3235.cpp // compile with: /clr generic<class T> public ref class C {}; generic<> public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.  
```