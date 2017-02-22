---
title: "컴파일러 경고 (수준 1) C4276 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4276"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4276"
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4276
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 프로토타입을 제공하지 않았습니다. 매개 변수가 없는 것으로 간주됩니다.  
  
 [\_\_stdcall](../../cpp/stdcall.md) 호출 규칙을 통해 함수의 주소를 받을 때에는 프로토타입을 제공하여 컴파일러에서 함수의 데코레이팅된 이름을 만들 수 있도록 해야 합니다.  *function*에 프로토타입이 없으므로 컴파일러에서는 데코레이팅된 이름을 만들 때 함수에 매개 변수가 없는 것으로 간주합니다.