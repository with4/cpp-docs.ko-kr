---
title: "유니코드: 와이드 문자 집합 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "유니코드[C++], 와이드 문자 집합"
  - "와이드 문자[C++], Unicode"
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 유니코드: 와이드 문자 집합
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

와이드 문자는 2바이트 다국어 문자 코드입니다.  전 세계의 현대식 컴퓨팅 환경에서 사용되는 모든 문자\(전문 기호 및 특수 출판 문자 포함\)는 유니코드 사양에 따라 와이드 문자로 표현될 수 있습니다.  Microsoft를 포함하는 대규모 컨소시엄으로 유지되고 발전된 유니코드 표준은 이제 널리 사용됩니다.  
  
 와이드 문자는 `wchar_t` 형식입니다.  와이드 문자열은 `wchar_t[]` 배열로 표현되고 `wchar_t*` 포인터로 지정됩니다.  모든 ASCII 문자는 문자 앞에 문자 `LL`을 접두사로 사용하여 와이드 문자로 나타낼 수 있습니다.  예를 들어, L'\\0'은 종료 와이드\(16비트\) `NULL` 문자입니다.  마찬가지로 모든 ASCII 문자열 리터럴은 ASCII 리터럴 앞에 문자 L을 접두사로 사용하여\(예: L"Hello"\) 간단하게 와이드 문자열 리터럴로 나타낼 수 있습니다.  
  
 일반적으로 와이드 문자는 멀티바이트 문자보다 메모리 공간을 더 많이 차지하지만 처리 속도는 더 빠릅니다.  또한 멀티바이트 인코딩에서는 한번에 한 개의 로캘만을 표현할 수 있지만 유니코드 표현에서는 전 세계의 모든 문자 집합을 동시에 표현할 수 있습니다.  
  
## 참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)