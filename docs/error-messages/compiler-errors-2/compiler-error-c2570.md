---
title: "컴파일러 오류 C2570 | Microsoft Docs"
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
  - "C2570"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2570"
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2570
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 공용 구조체에서 기본 클래스를 사용할 수 없습니다.  
  
 공용 구조체가 클래스, 구조체 또는 공용 구조체로부터 파생되었습니다.  이것은 허용되지 않습니다.  대신에 파생된 형식을 클래스나 구조체로 선언하십시오.  
  
 다음 샘플에서는 C2570 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2570.cpp  
// compile with: /c  
class base {};  
union hasPubBase : public base {};   // C2570  
union hasNoBase {};   // OK  
```