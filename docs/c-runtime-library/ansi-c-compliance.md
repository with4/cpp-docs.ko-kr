---
title: "ANSI C 규격 | Microsoft Docs"
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
  - "Ansi"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ANSI[C++], C 표준"
  - "호환성[C++], ANSI C"
  - "ANSI C 규격"
  - "규칙[C++], Microsoft 확장"
  - "Microsoft 확장 명명 규칙"
  - "명명 규칙[C++], Microsoft 라이브러리"
  - "밑줄"
  - "밑줄, 줄 간격"
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ANSI C 규격
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

런타임 시스템\(예: 함수, 매크로, 상수, 변수 및 형식 정의\)의 모든 Microsoft 고유의 식별자에 대한 명명 규칙은 ANSI 규격입니다.  이 설명서에서는 ANSI\/ISO C 표준을 따르는 모든 런타임 함수는 ANSI 호환 되는 것으로 기록됩니다.  ANSI 호환 응용 프로그램은 이러한 ANSI 호환 함수를 사용해야 합니다.  
  
 Microsoft 고유의 함수 및 전역 변수 이름은 단일 밑줄로 시작합니다.  이러한 이름은 코드의 범위 내에서 오직 로컬에 재정의할 수 있습니다.  예를 들어, Microsoft 런타임 헤더 파일을 포함할 때, 같은 이름의 지역 변수를 선언함으로써 여전히 로컬에 `_open`라는 이름의 Microsoft 고유의 함수를 재정의할 수 있습니다.  그러나, 이 이름을 자신의 전역 함수나 전역 변수에 사용할 수 없습니다.  
  
 Microsoft 고유의 매크로 및 매니페스트 상수의 이름은 두 밑줄로 시작하거나 단일 선행 밑줄과 바로 이어지는 대문자로 시작합니다.  이 식별자의 범위는 절대입니다.  예를들어, 이 이유로 Microsoft 고유의 식별자 **\_UPPER**를 사용할 수 없습니다.  
  
## 참고 항목  
 [호환성](../c-runtime-library/compatibility.md)