---
title: "컴파일러 오류 C2010 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2010"
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'character' : 매크로 정식 매개 변수 목록에 사용할 수 없습니다.  
  
 매크로 정의에 대한 정식 매개 변수 목록에서 문자가 잘못 사용되었습니다.  이 오류를 해결하려면 해당 문자를 제거하십시오.  
  
 다음 샘플에서는 C2010 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```