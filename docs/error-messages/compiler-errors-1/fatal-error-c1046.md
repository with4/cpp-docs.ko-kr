---
title: "심각한 오류 C1046 | Microsoft Docs"
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
  - "C1046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1046"
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 구조체가 너무 많이 중첩되었습니다.  
  
 구조체, 공용 구조체 또는 클래스가 중첩 한계 수준인 15를 초과했습니다.  정의를 다시 작성하여 중첩 수준을 줄이십시오.  하나 이상의 중첩 구조체를 `typedef` 를 사용하여 정의하는 방법으로 구조체, 공용 구조체 또는 클래스를 둘 이상의 부분으로 분할하십시오.