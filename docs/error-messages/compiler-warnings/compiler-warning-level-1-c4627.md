---
title: "컴파일러 경고(수준 1) C4627 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4627"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4627"
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4627
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<identifier\>': 미리 컴파일된 헤더 사용을 찾을 때 건너뛰었습니다.  
  
 미리 컴파일된 헤더가 사용되는 위치를 검색하는 동안 컴파일러에서 *\<identifier\>* 포함 파일에 대한 `#include` 지시문이 발생했습니다. 미리 컴파일된 헤더에 *\<identifier\>* 포함 파일이 없는 경우 컴파일러는 `#include` 지시문을 무시하지만 **C4627** 경고가 발생합니다.  
  
## 참고 항목  
 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)