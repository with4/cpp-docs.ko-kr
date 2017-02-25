---
title: "컴파일러 오류 C2500 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2500"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2500"
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2500
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1' : 'identifier2'은\(는\) 이미 직접 기본 클래스입니다.  
  
 클래스 또는 구조체가 기본 클래스 목록에 두 번 이상 표시됩니다.  
  
 직접 기본 클래스는 기본 목록에 표시되는 클래스이며,  간접 기본 클래스는 기본 목록에 있는 클래스에 대한 기본 클래스입니다.  
  
 클래스는 직접 기본 클래스로 두 번 이상 지정할 수 없지만,  간접 기본 클래스로 두 번 이상 사용할 수 있습니다.  
  
 다음 샘플에서는 C2500 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```