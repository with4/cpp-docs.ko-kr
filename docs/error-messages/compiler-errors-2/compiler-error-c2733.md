---
title: "컴파일러 오류 C2733 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2733"
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오버로드된 함수 'function'의 두 번째 C 링크는 허용되지 않습니다.  
  
 둘 이상의 오버로드된 함수가 C 링크로 선언되었습니다.  C 링크를 사용할 경우, 지정한 함수에 대한 하나의 형식만 외부 형식이 될 수 있습니다.  오버로드된 함수들은 데코레이팅되지 않은 동일 이름을 사용하므로 C 프로그램에서 사용할 수 없습니다.  
  
 다음 샘플에서는 C2733 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```