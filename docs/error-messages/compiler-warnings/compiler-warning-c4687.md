---
title: "컴파일러 경고 C4687 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4687"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4687"
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 경고 C4687
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 봉인 추상 클래스는 'interface' 인터페이스를 구현할 수 없습니다.  
  
 봉인된 추상 형식은 일반적으로 정적 멤버 함수를 유지하는 데만 사용됩니다.  
  
 자세한 내용은 [abstract](../../windows/abstract-cpp-component-extensions.md) 및 [sealed](../../windows/sealed-cpp-component-extensions.md)를 참조하십시오.  
  
 기본적으로 C4687은 오류로 발생합니다.  [경고](../../preprocessor/warning.md) pragma를 사용하면 C4687 경고를 표시하지 않을 수 있습니다.  봉인된 추상 형식으로 인터페이스를 구현해야만 하는 경우 C4687을 해제할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C4687 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```