---
title: "STACKSIZE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "STACKSIZE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACKSIZE .def 파일 문"
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# STACKSIZE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스택 크기를 바이트 단위로 설정합니다.  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## 설명  
 이와 동일한 스택 설정 방법은 [스택 할당](../../build/reference/stack-stack-allocations.md)\(\/STACK\) 옵션을 사용하는 것입니다.  *reserve* 및 `commit` 인수에 대한 자세한 내용은 해당 옵션의 설명 부분을 참조하십시오.  
  
 DLL에는 이 옵션이 적용되지 않습니다.  
  
## 참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)