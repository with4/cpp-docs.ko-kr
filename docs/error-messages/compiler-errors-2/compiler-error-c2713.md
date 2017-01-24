---
title: "컴파일러 오류 C2713 | Microsoft Docs"
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
  - "C2713"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2713"
ms.assetid: bae9bee3-b4b8-4be5-b6a5-02df587a7278
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2713
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예외 처리 형식은 함수 당 하나씩만 허용됩니다.  
  
 구조적 예외 처리\(`__try`\/`__except`\)와 C\+\+ 예외 처리\(`try`\/`catch`\)를 동일 함수에서 사용할 수 없습니다.