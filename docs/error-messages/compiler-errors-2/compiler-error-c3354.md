---
title: "컴파일러 오류 C3354 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3354"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3354"
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3354
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 대리자를 만드는 데 사용되는 함수는 'type' 반환 형식을 사용할 수 없습니다.  
  
 다음 형식은 [위임](../../misc/delegate.md)에 대한 반환 형식으로 부적합합니다.  
  
-   함수 포인터  
  
-   멤버 포인터  
  
-   멤버 함수에 대한 포인터  
  
-   함수에 대한 참조  
  
-   멤버 함수에 대한 참조  
  
 다음 샘플에서는 C3354를 생성합니다.  
  
```  
// C3354_2.cpp // compile with: /clr /c using namespace System; typedef void ( *VoidPfn )(); delegate VoidPfn func(); // C3354 // try the following line instead // delegate  void func();  
```  
  
 다음 샘플에서는 C3354를 생성합니다.  
  
```  
// C3354.cpp // compile with: /clr:oldSyntax /c #using <mscorlib.dll> using namespace System; typedef void (*VoidPfn)(); __delegate VoidPfn func();   // C3354 // try the following line instead // __delegate void func();  
```