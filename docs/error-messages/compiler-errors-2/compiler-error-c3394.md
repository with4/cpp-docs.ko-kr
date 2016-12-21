---
title: "컴파일러 오류 C3394 | Microsoft Docs"
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
  - "C3394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3394"
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제약 조건 절의 구문 오류: 형식이 필요한데 'identifier'가 있습니다.  
  
 제약 조건 형식이 잘못되었습니다.  자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3394를 생성합니다.  
  
```  
// C3394.cpp // compile with: /clr /c ref class MyClass {}; ref class R { generic<typename T> where T : static   // C3394 // try the following line instead // where T : MyClass void f() {} };  
```