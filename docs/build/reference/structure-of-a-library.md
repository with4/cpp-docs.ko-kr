---
title: "라이브러리 구조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "라이브러리, 구조"
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 라이브러리 구조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

라이브러리에는 COFF 개체가 들어 있습니다.  라이브러리의 개체에는 프로그램의 다른 개체가 외부적으로 참조할 수 있는 함수 및 데이터가 들어 있습니다.  라이브러리에 들어 있는 개체는 때때로 라이브러리 멤버라고 합니다.  
  
 DUMPBIN 도구를 \/LINKERMEMBER 옵션으로 실행하면 라이브러리의 내용에 대한 추가 정보를 볼 수 있습니다.  이 옵션에 대한 자세한 내용은 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)를 참조하십시오.  
  
## 참고 항목  
 [LIB 개요](../../build/reference/overview-of-lib.md)