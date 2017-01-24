---
title: "컴파일러 오류 C3400 | Microsoft Docs"
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
  - "C3400"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3400"
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3400
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constraint\_1' 및 'constraint\_2'와 관련된 순환 제약 조건 종속성입니다.  
  
 컴파일러가 순환 제약 조건을 검색했습니다.  
  
 자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3400을 생성합니다.  
  
```  
// C3400.cpp // compile with: /clr /c generic<class T, class U> where T : U where U : T   // C3400 public ref struct R {};  
```