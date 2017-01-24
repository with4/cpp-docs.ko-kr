---
title: "컴파일러 오류 C2458 | Microsoft Docs"
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
  - "C2458"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2458"
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2458
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 정의 내에 재정의가 있습니다.  
  
 클래스, 구조체, 공용 구조체 또는 열거형이 자체 선언 내에서 재정의됩니다.  
  
 다음 샘플에서는 C2458 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2458.cpp  
class C {  
   enum i { C };   // C2458  
};  
```