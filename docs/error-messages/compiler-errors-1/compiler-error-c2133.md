---
title: "컴파일러 오류 C2133 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2133"
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 알 수 없는 크기입니다.  
  
 크기를 지정하지 않은 배열은 클래스, 구조체, 공용 구조체 또는 열거형의 멤버로 선언됩니다.  크기를 지정하지 않은 멤버 배열에 \/Za\(ANSI C\) 옵션을 사용할 수 없습니다.  
  
 다음 샘플에서는 C2133 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2133.cpp  
// compile with: /Za  
struct X {  
   int a[0];   // C2133 unsized array  
};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2133b.cpp  
// compile with: /c  
struct X {  
   int a[0];   // no /Za  
};  
```