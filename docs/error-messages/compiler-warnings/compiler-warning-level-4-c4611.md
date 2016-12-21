---
title: "컴파일러 경고 (수준 4) C4611 | Microsoft Docs"
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
  - "C4611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4611"
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' 및 C\+\+ 개체 소멸 사이의 상호 작용이 이식 가능하지 않습니다.  
  
 일부 플랫폼에서는 **catch**를 포함하고 있는 함수가 범위를 벗어날 때 C\+\+ 개체 소멸 의미를 지원하지 않을 수 있습니다.  
  
 예기치 않은 동작이 발생하지 않도록 하려면 생성자와 소멸자가 있는 함수에 **catch**를 사용하지 않도록 합니다.  
  
 이 경고는 한 번만 발생합니다. [pragma warning](../../preprocessor/warning.md)을 참조하십시오.