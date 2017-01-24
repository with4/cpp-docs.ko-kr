---
title: "NMAKE 심각한 오류 U1070 | Microsoft Docs"
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
  - "U1070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1070"
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 심각한 오류 U1070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'macroname' 매크로 정의에서 순환됩니다.  
  
 지정한 매크로 정의에 정의가 해당 매크로에 포함되는 매크로가 포함되어 있습니다.  순환 매크로 정의가 잘못되었습니다.  
  
## 예제  
 예를 들면, 매크로 정의는 다음과 같습니다.  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 위 매크로 정의는 다음 오류를 발생시킵니다.  
  
```  
cycle in macro definition 'TWO'  
```