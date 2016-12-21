---
title: "컴파일러 오류 C2379 | Microsoft Docs"
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
  - "C2379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2379"
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 매개 변수 번호의 형식이 다릅니다.  
  
 지정한 매개 변수의 형식은 기본 확장이긴 하지만 이전 선언에서의 형식과 호환되지 않습니다.  이는 ANSI C\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 오류이며 Microsoft 확장\(**\/Ze**\)에서는 경고입니다.  
  
 다음 샘플에서는 C2379 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```