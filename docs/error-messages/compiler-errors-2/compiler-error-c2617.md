---
title: "컴파일러 오류 C2617 | Microsoft Docs"
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
  - "C2617"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2617"
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2617
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : return 문이 일관성이 없습니다.  
  
 지정한 함수가 선언된 반환 형식을 사용하지 않으며 이전 return 문이 값을 제공하지 않았습니다.  
  
 다음 샘플에서는 C2617 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2617.cpp  
int i;  
func() {   // no return type prototype  
   if( i ) return;   // no return value  
   else return( 1 );   // C2617 detected on this line  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2617b.cpp  
// compile with: /c  
int i;  
int MyF() {  
   if (i)  
      return 0;  
   else   
      return (1);  
}  
```