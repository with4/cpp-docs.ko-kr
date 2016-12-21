---
title: "컴파일러 오류 C2129 | Microsoft Docs"
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
  - "C2129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2129"
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' 정적 함수를 선언했으나 정의하지 않았습니다.  
  
 정의되지 않은 `static` 함수에 대한 전방 참조를 수행했습니다.  
  
 `static` 함수는 파일 범위 내에서 정의해야 합니다.  다른 파일에 정의한 함수는 `extern`으로 선언해야 합니다.