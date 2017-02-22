---
title: "컴파일러 오류 C3388 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3388"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3388"
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 오류 C3388
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 제약 조건으로 사용할 수 없습니다. 구문 분석을 계속하기 위해 'ref class'로 간주합니다.  
  
 제약 조건이 제네릭 형식에 지정되었지만 제약 조건을 올바르게 지정하지 않았습니다. 자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3388을 생성합니다.  
  
```  
// C3388.cpp // compile with: /clr /c interface class AA {}; generic <class T> where T : interface class   // C3388 ref class C {}; // OK generic <class T> where T : AA ref class D {};  
```