---
title: "컴파일러 오류 C2410 | Microsoft Docs"
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
  - "C2410"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2410"
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2410
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'context'의 멤버 이름이 모호합니다.  
  
 식별자가 이 컨텍스트에서 둘 이상의 구조체 또는 공용 구조체의 멤버입니다.  
  
 오류를 발생시킨 피연산자에 구조체 또는 공용 구조체 지정자를 사용하십시오.  구조체 또는 공용 구조체 지정자는 `struct` 또는 `union` 형식의 식별자입니다\(참조되는 구조체 또는 공용 구조체와 형식이 동일한 변수 또는 `typedef`이름\).  피연산자를 사용하려면 지정자가 첫 번째 멤버 선택 연산자\(.\)의 왼쪽 피연산자여야 합니다.