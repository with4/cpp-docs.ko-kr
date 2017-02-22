---
title: "컴파일러 오류 C2516 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2516"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2516"
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2516
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 올바른 기본 클래스가 아닙니다.  
  
 클래스가 `typedef` 문에 의해 정의된 형식 이름에서 파생되었습니다.  
  
 다음 샘플에서는 C2516 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2516.cpp  
typedef unsigned long ulong;  
class C : public ulong {}; // C2516  
```