---
title: "컴파일러 오류 C2460 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2460"
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1' : 정의 중인 'identifier2'을\(를\) 사용합니다.  
  
 클래스 또는 구조체\(`identifier2`\)가 자체 멤버\(`identifier1`\)로서 선언되었습니다.  클래스 및 구조체의 재귀 정의는 사용할 수 없습니다.  
  
 다음 샘플에서는 C2460 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 대신 클래스에서 포인터 참조를 사용합니다.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```