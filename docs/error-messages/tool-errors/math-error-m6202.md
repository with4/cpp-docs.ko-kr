---
title: "수학 오류 M6202 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6202"
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 수학 오류 M6202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : \_SING 오류  
  
 지정한 함수에 대한 인수가 해당 함수에 대한 특이 값입니다.  함수는 이 인수에 대해 정의되어 있지 않습니다.  
  
 이 오류는 함수 이름, 해당 인수 및 오류 유형을 가진 `_matherr` 함수를 호출합니다.  특정 런타임 부동 소수점의 수학 오류 처리를 사용자 지정하려면 `_matherr` 함수를 다시 씁니다.