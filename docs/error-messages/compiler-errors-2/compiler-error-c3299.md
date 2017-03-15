---
title: "컴파일러 오류 C3299 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3299"
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 컴파일러 오류 C3299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member\_function': 제약 조건을 지정할 수 없습니다. 제약 조건이 기본 메서드에서 상속되었습니다.  
  
 제네릭 멤버 함수를 재정의하는 경우 제약 조건 절을 지정할 수 없습니다\(제약 조건 반복은 제약 조건이 상속되지 않음을 나타냄\).  
  
 재정의하는 제네릭 함수의 제약 조건 절이 상속됩니다.  
  
 자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3299를 생성합니다.  
  
```  
// C3299.cpp // compile with: /clr /c public ref struct R { generic<class T> where T : R virtual void f(); }; public ref struct S : R { generic<class T> where T : R   // C3299 virtual void f() override; };  
```