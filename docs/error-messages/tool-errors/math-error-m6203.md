---
title: "수학 오류 M6203 | Microsoft Docs"
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
  - "M6203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6203"
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 수학 오류 M6203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : \_OVERFLOW 오류  
  
 지정한 함수의 결과가 너무 커서 나타낼 수 없습니다.  
  
 이 오류는 함수 이름, 해당 인수 및 오류 유형을 가진 `_matherr` 함수를 호출합니다.  특정 런타임 부동 소수점의 수학 오류 처리를 사용자 지정하려면 `_matherr` 함수를 다시 씁니다.