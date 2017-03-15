---
title: "컴파일러 오류 C3393 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3393"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3393"
ms.assetid: d57f7c69-0a02-4fe3-9e45-bc62644fd77c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3393
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제약 조건 절의 구문 오류: 'identifier'가 형식이 아닙니다.  
  
 제약 조건에 전달된 식별자가 형식이어야 하는 데 형식이 아닙니다.  자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3393을 생성합니다.  
  
```  
// C3393.cpp // compile with: /clr /c void MyInterface() {} interface class MyInterface2 {}; generic<typename T> where T : MyInterface   // C3393 // try the following line instead // where T : MyInterface2 ref class R {};  
```