---
title: "NMAKE 매크로 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "매크로, NMAKE"
  - "NMAKE 매크로, using"
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 매크로 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

매크로를 사용하려면 다음과 같이 달러 기호\($\) 다음에 매크로 이름을 괄호로 묶습니다.  
  
## 구문  
  
```  
$(macroname)  
```  
  
## 설명  
 공백은 사용할 수 없습니다.  *macroname*이 단일 문자인 경우 괄호를 생략할 수 있습니다.  정의 문자열은 $\(*macroname*\)을 대신하고 정의되지 않은 매크로는 null 문자열로 바뀝니다.  
  
## 추가 정보  
 [매크로 대체](../build/macro-substitution.md)  
  
## 참고 항목  
 [매크로와 NMake](../build/macros-and-nmake.md)