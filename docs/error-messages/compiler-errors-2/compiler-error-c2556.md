---
title: "컴파일러 오류 C2556 | Microsoft Docs"
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
  - "C2556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2556"
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 오버로드된 함수가 반환 형식만 다릅니다.  
  
 오버로드된 함수들의 반환 형식은 각기 다르지만 매개 변수 목록은 동일합니다.  오버로드된 각 함수는 고유한 정식 매개 변수 목록을 사용해야 합니다.  
  
 다음 샘플에서는 C2556 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2556.cpp  
// compile with: /c  
class C {  
   int func();  
   double func();   // C2556  
   int func(int i);   // ok parameter lists differ  
};  
```