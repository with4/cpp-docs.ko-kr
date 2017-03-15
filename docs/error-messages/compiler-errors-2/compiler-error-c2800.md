---
title: "컴파일러 오류 C2800 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2800"
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator'을\(를\) 오버로드할 수 없습니다.  
  
 클래스 멤버 액세스\(`.`\), 멤버에 대한 포인터\(`.*`\), 범위 결정\(`::`\), 조건식\(`? :`\) 및 `sizeof` 연산자는 오버로드할 수 없습니다.  
  
 다음 샘플에서는 C2800 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```