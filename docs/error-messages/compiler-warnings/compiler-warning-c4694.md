---
title: "컴파일러 경고 C4694 | Microsoft Docs"
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
  - "C4694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4694"
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class\_1': 봉인 추상 클래스는 기본 클래스 'base\_class'를 포함할 수 없습니다.  
  
 추상 및 봉인 클래스가 참조 형식에서 상속할 수 없습니다. 추상 및 봉인 클래스는 기본 클래스 함수를 구현할 수도 없고 스스로를 기본 클래스로 사용할 수도 없습니다.  
  
 자세한 내용은 [abstract](../../windows/abstract-cpp-component-extensions.md), [sealed](../../windows/sealed-cpp-component-extensions.md) 및 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C4694를 생성합니다.  
  
```  
// C4694.cpp // compile with: /c /clr ref struct A {}; ref struct B sealed abstract : A {};   // C4694  
```