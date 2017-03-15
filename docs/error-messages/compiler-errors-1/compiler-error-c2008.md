---
title: "컴파일러 오류 C2008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2008"
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'character' : 매크로 정의에 사용할 수 없습니다.  
  
 문자가 매크로 이름 바로 다음에 표시됩니다.  이 오류를 해결하려면 매크로 이름 다음에 공백을 하나 두어야 합니다.  
  
 다음 샘플에서는 C2008 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```