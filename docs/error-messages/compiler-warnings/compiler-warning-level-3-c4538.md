---
title: "컴파일러 경고 (수준 3) C4538 | Microsoft Docs"
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
  - "C4538"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4538"
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4538
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 이 형식에 대해서는 const\/volatile 한정자를 사용할 수 없습니다.  
  
 한정자 키워드가 배열에 잘못 적용되었습니다.  자세한 내용은 [배열](../../windows/arrays-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C4538 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4538.cpp  
// compile with: /clr /W3 /LD  
const array<int> ^f1();   // C4538  
array<const int> ^f2();   // OK  
```