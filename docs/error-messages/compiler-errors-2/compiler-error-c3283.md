---
title: "컴파일러 오류 C3283 | Microsoft Docs"
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
  - "C3283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3283"
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 인터페이스에는 인스턴스 생성자를 사용할 수 없습니다.  
  
 CLR [인터페이스](../../windows/interface-class-cpp-component-extensions.md)에는 인스턴스 생성자를 사용할 수 없습니다.  정적 생성자는 허용됩니다.  
  
 다음 샘플에서는 C3283을 생성합니다.  
  
```  
// C3283.cpp // compile with: /clr interface class I { I();   // C3283 };  
```  
  
 해결 방법:  
  
```  
// C3283b.cpp // compile with: /clr /c interface class I { static I(){} };  
```