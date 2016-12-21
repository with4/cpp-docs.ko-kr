---
title: "컴파일러 오류 C3413 | Microsoft Docs"
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
  - "C3413"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3413"
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3413
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': 잘못된 명시적 인스턴스화입니다.  
  
 컴파일러가 잘못된 형식의 명시적 인스턴스화를 검색했습니다.  
  
 다음 샘플에서는 C3413을 생성합니다.  
  
```  
// C3413.cpp template class MyClass {};   // C3413  
```  
  
 해결 방법:  
  
```  
// C3413b.cpp // compile with: /c template <class T> class MyClass {}; template <> class MyClass<int> {};  
```