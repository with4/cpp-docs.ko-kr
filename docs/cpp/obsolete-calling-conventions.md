---
title: "사용되지 않는 호출 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__fortran"
  - "__pascal"
  - "__syscall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__fortran 키워드[C++]"
  - "__pascal 키워드[C++]"
  - "__syscall 키워드[C++]"
  - "호출 규칙, 사용되지 않음"
  - "WINAPI"
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 사용되지 않는 호출 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 **\_\_pascal**, **\_\_fortran** 및 **\_\_syscall** 호출 규칙은 더 이상 지원되지 않습니다.  지원되는 호출 규칙 및 적절한 링커 옵션 중 하나를 사용하여 해당 기능을 에뮬레이트할 수 있습니다.  
  
 현재 WINDOWS.H는 대상에 대해 적절한 호출 규칙으로 변환하는 **WINAPI** 매크로를 지원합니다.  이전에 **PASCAL** 또는 **\_\_far \_\_pascal**을 사용했던 **WINAPI**를 사용합니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)