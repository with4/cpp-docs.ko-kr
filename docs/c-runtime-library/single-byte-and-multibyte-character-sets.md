---
title: "싱글바이트 및 멀티바이트 문자 집합 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "문자 집합[C++], 멀티바이트"
  - "문자 집합[C++], 싱글바이트"
  - "MBCS[C++], MBCS 정보"
  - "SBCS(싱글바이트 문자 집합)"
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 싱글바이트 및 멀티바이트 문자 집합
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ASCII 문자 집합은 0x00 – 0x7F 범위에서 문자를 정의합니다.  주로 유럽의 문자 집합의 수에서는 ASCII 문자 집합과 동일하게 0x00 – 0x7F 범위에서 문자를 정의할 뿐만 아니라 0x80 – 0xFF 범위의 확장 문자를 정의합니다.  따라서 ASCII 문자 집합은 물론 많은 유럽 언어의 문자 집합을 표현하는 데에는 8비트의 `SBCS`\(싱글바이트 문자 집합\)만으로도 충분합니다.  그러나 한국어와 같은 일부 비 유럽 문자 집합에는 싱글바이트 코드 구성표로 표현할 수 있는 것보다 많은 문자가 있기 때문에 `MBCS`\(멀티바이트 문자 집합\) 인코딩이 필요합니다.  
  
> [!NOTE]
>  Microsoft 런타임 라이브러리에서 많은 `SBCS` 루틴은 멀티 바이트 바이트, 문자 및 문자열을 적절하게 처리합니다.  많은 멀티 바이트 문자 집합은 ASCII 문자 집합을 부분 집합으로 정의합니다.  많은 멀티바이트 문자 집합에서 0x00 – 0x7F 범위에 있는 각 문자는 ASCII 문자 집합에서 동일한 값을 갖는 문자와 같습니다.  예를 들어, `ASCII` 및 `MBCS` 문자 문자열에서 1 바이트 `NULL` 문자\('\\0'\) 은 0x00 을 가지로 종료 null 문자를 나타냅니다.  
  
 멀티 바이트 문자 집합은 1 바이트와 2 바이트 문자로 구성 될 수 있습니다.  따라서 멀티 바이트 문자열은 싱글바이트 및 더블 바이트 문자를 함께 포함 할 수 있습니다.  두 바이트 멀티 바이트 문자는 후행 바이트와 선행 바이트를 가집니다.  특정 멀티바이트 문자 집합에서 선행 바이트는 후행 바이트와 마찬가지로 일정한 범위 안에 포함됩니다.  이러한 범위가 겹치는 경우에는 특정 바이트가 선행 바이트인지 후행 바이트인지를 특정한 상황에 따라 판단해야 합니다.  
  
## 참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)