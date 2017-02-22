---
title: "캐스팅 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "캐스팅 연산자"
  - "연산자[C++], 캐스팅"
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 캐스팅 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

캐스트 연산자에는 C\+\+ 언어 전용 연산자가 몇 가지 있습니다.  이 연산자는 예전 스타일의 C 언어 캐스트에 있는 일부 모호함과 위험성을 제거하는 데 목적이 있습니다.  그 종류는 다음과 같습니다.  
  
-   [dynamic\_cast](../cpp/dynamic-cast-operator.md) 다형 형식을 변환하는 데 사용됩니다.  
  
-   [static\_cast](../cpp/static-cast-operator.md) 비다형 형식을 변환하는 데 사용됩니다.  
  
-   [const\_cast](../cpp/const-cast-operator.md) `const`, `volatile` 및 `__unaligned` 특성을 제거하는 데 사용됩니다.  
  
-   [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) 비트의 단순 재해석에 사용됩니다.  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) 확인할 수 있는 MSIL을 생성하는 데 사용됩니다.  
  
 `const_cast` 및 `reinterpret_cast`는 이전 스타일의 캐스트와 동일한 위험을 보유하고 있으므로 마지막 수단으로 사용합니다.  하지만 이 두 캐스트는 이전 스타일 캐스트를 완전히 바꾸기 위해 여전히 필요합니다.  
  
## 참고 항목  
 [캐스팅](../cpp/casting.md)