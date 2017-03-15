---
title: "NMake 매크로 정의 | Microsoft Docs"
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
  - "NMAKE 매크로 정의"
  - "매크로, NMAKE"
  - "NMAKE 매크로, 정의"
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# NMake 매크로 정의
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
macroname=string  
```  
  
## 설명  
 *macroname*은 문자, 숫자 및 밑줄을 최대 1,024자까지 결합한 것이며 대\/소문자를 구분합니다.  *macroname*에 호출된 매크로가 포함될 수 있습니다.  *macroname*이 호출된 매크로만으로 구성된 경우 호출 중인 매크로는 null 또는 정의되지 않은 매크로가 될 수 없습니다.  
  
 `string`은 0개 이상의 문자로 구성된 시퀀스입니다.  null 문자열에는 0개의 문자 또는 공백이나 탭만 포함됩니다.  `string`에 매크로 호출이 포함될 수 있습니다.  
  
## 추가 정보  
 [매크로의 특수 문자](../build/special-characters-in-macros.md)  
  
 [null 및 정의되지 않은 매크로](../build/null-and-undefined-macros.md)  
  
 [매크로를 정의할 위치](../build/where-to-define-macros.md)  
  
 [매크로 정의의 우선 순위](../build/precedence-in-macro-definitions.md)  
  
## 참고 항목  
 [매크로와 NMake](../build/macros-and-nmake.md)