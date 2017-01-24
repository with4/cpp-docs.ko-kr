---
title: "컴파일러 오류 C3187 | Microsoft Docs"
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
  - "C3187"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3187"
ms.assetid: 9d2ebf55-1a6a-4087-bf5b-5274baae6351
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3187
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_func\_\_': 함수의 본문 내에서만 사용할 수 있습니다.  
  
 미리 정의된 매크로는 함수의 본문 밖에서 사용할 수 없습니다.  
  
 이 오류를 해결하려면 함수의 본문 안으로 매크로를 이동합니다.