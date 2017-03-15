---
title: "컴파일러 경고 (수준 3) C4278 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4278"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4278"
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 3) C4278
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 형식 라이브러리 'tlb'의 식별자가 이미 매크로입니다. 'rename' 한정자를 사용하십시오.  
  
 [\#import](../../preprocessor/hash-import-directive-cpp.md)를 사용할 때 가져오는 typelib의 식별자에서 식별자 ***identifier***을\(를\) 선언하려고 했습니다.  하지만 해당 식별자가 이미 올바른 기호입니다.  
  
 `#import` **rename** 특성을 사용하여 형식 라이브러리의 기호에 별칭을 할당하십시오.