---
title: "컴파일러 오류 C3363 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3363"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3363"
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3363
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 'typeid'는 형식에만 적용될 수 있습니다.  
  
 [typeid](../../windows/typeid-cpp-component-extensions.md) 연산자를 잘못 사용했습니다.  
  
## 예제  
 다음 샘플에서는 C3363을 생성합니다.  
  
```  
// C3363.cpp // compile with: /clr int main() { System::typeid;   // C3363 }  
```