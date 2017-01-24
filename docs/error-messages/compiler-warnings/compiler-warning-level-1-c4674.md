---
title: "컴파일러 경고(수준 1) C4674 | Microsoft Docs"
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
  - "C4674"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4674"
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4674
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method'는 'static'으로 선언해야 하며 하나의 매개 변수만 가져야 합니다.  
  
 변환 연산자의 서명이 잘못되었습니다. 메서드는 사용자 정의 변환으로 간주되지 않습니다.  
  
 새로운 구문\(**\/clr**\)을 사용하는 경우 연산자 정의에 대한 자세한 내용은 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md) 및 [사용자 정의 변환](../../dotnet/user-defined-conversions-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C4674를 생성합니다.  
  
```  
// C4674.cpp // compile with: /clr /WX /W1 /LD ref class G { int op_Implicit(int i) {   // C4674 return 0; } };  
```  
  
## 예제  
 다음 샘플에서는 C4674를 생성합니다.  
  
```  
// C4674_b.cpp // compile with: /clr:oldSyntax /W1 /LD __gc class G { int op_Implicit(int i) {   // C4674 // try the following line instead // static int op_Implicit(int i) { return 0; } };  
```