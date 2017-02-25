---
title: "컴파일러 경고 (수준 1) C4420 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4420"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4420"
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4420
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 연산자를 사용할 수 없어 'operator'을\(를\) 대신 사용합니다. 런타임 검사가 손상되었을 수 있습니다.  
  
 이 경고는 벡터 new\/delete 검사를 수행하는 [\/RTCv](../../build/reference/rtc-run-time-error-checks.md)를 사용할 때와 벡터 형식이 없을 때 발생합니다.  이 경우 벡터가 아닌 형식을 사용했습니다.  
  
 \/RTCv가 올바로 작동하려면 벡터 구문을 사용한 경우 컴파일러에서 항상 [new](../../cpp/new-operator-cpp.md)\/[delete](../../cpp/delete-operator-cpp.md) 벡터 형식을 호출해야 합니다.