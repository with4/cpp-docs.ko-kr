---
title: "컴파일러 오류 C3399 | Microsoft Docs"
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
  - "C3399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3399"
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 제네릭 매개 변수의 인스턴스를 만들 때는 인수를 지정할 수 없습니다.  
  
 `gcnew()` 제약 조건을 지정할 때 제약 조건 형식이 매개 변수가 없는 생성자를 갖도록 지정합니다. 따라서 해당 형식을 인스턴스화하고 매개 변수를 전달하려고 하면 오류가 발생합니다.  
  
 자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3399를 생성합니다.  
  
```  
// C3399.cpp // compile with: /clr /c generic <class T> where T : gcnew() void f() { T t = gcnew T(1);   // C3399 T t2 = gcnew T();   // OK }  
```