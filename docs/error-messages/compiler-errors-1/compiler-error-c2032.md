---
title: "컴파일러 오류 C2032 | Microsoft Docs"
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
  - "C2032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2032"
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 함수는 구조체\/공용 구조체 'structorunion'의 멤버일 수 없습니다.  
  
 구조체나 공용 구조체에는, C\+\+에서는 사용할 수 있지만 C에서는 사용할 수 없는 멤버 함수가 포함되어 있습니다.  이 오류를 해결하려면 C\+\+ 프로그램으로 컴파일하거나 멤버 함수를 제거하십시오.  
  
 다음 샘플에서는 C2032 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```