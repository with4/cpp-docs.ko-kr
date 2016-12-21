---
title: "컴파일러 오류 C3297 | Microsoft Docs"
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
  - "C3297"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3297"
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3297
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constraint\_2': 'constraint\_1'에 값 제약 조건이 있으므로 'constraint\_1'을 제약 조건으로 사용할 수 없습니다.  
  
 값 클래스가 봉인되어 있습니다. 제약 조건이 값 클래스인 경우 다른 제약 조건이 파생될 수 없습니다.  
  
 자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3297을 생성합니다.  
  
```  
// C3297.cpp // compile with: /clr /c generic<class T, class U> where T : value class where U : T   // C3297 public ref struct R {};  
```