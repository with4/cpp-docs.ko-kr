---
title: "컴파일러 오류 C3266 | Microsoft Docs"
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
  - "C3266"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3266"
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3266
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 클래스\-생성자에는 'void' 매개 변수 목록이 있어야 합니다.  
  
 \/clr 프로그래밍을 사용하는 클래스의 클래스\-생성자는 매개 변수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C3266을 생성합니다.  
  
```  
// C3266.cpp // compile with: /clr ref class X { static X(int i) { // C3266 // try the following line instead // static X() { } }; int main() { }  
```  
  
 다음 샘플에서는 C3266을 생성합니다.  
  
```  
// C3266b.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc class X { static X(int i) { // C3266 // try the following line instead // static X() { } }; int main() { }  
```