---
title: "컴파일러 오류 C3384 | Microsoft Docs"
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
  - "C3384"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3384"
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3384
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_parameter': 값 제약 조건과 ref 제약 조건은 함께 사용할 수 없습니다.  
  
 제네릭 형식을 `value class` 및 `ref class` 둘 다로 제한할 수 없습니다.  
  
 자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3384를 생성합니다.  
  
```  
// C3384.cpp // compile with: /c /clr generic <typename T> where T : ref class where T : value class   // C3384 ref class List {};  
```