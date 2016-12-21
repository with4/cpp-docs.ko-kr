---
title: "C++ 주석 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "코드 주석, C++"
  - "주석, C++ 코드"
  - "주석, 코드 문서화"
  - "공백, C++ 주석"
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 주석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

주석은 컴파일러에서 무시되지만 프로그래머에게는 유용한 텍스트입니다.  주석은 나중에 참조할 수 있도록 코드에 주석을 추가하는 데 일반적으로 사용됩니다.  컴파일러는 이들을 공백으로 처리합니다.  특정 코드 줄을 비활성으로 만들면 테스트 시 메모를 사용할 수 있습니다. 그러나 주석이 포함 된 코드를 묶을 수는 있지만 주석은 중첩 될 수 없기 때문에 `#if`\/`#endif` 전처리기 지시문이 더 잘 작동합니다.  
  
 C\+\+ 주석은 다음 방법 중 하나로 기록됩니다.  
  
-   문자\(새로운 줄 포함\) 시퀀스 뒤에 오는 `/*`\(슬래시, 별표\) 문자는 `*/` 문자 뒤에 옵니다.  이 구문은 ANSI C와 같습니다.  
  
-   `//`  \(슬래시 두 개\) 문자 시퀀스 다음에 문자의 시퀀스가 옵니다.  백슬래시가 바로 앞에 오지 않는 새 줄은 이러한 형식의 주석을 종료합니다.  따라서 일반적으로 "한 줄 주석"이라고 합니다.  
  
 주석 문자\(`/*`, `*/` 및 `//`\)에는 문자 상수, 문자열 리터럴 또는 주석 안에서 특별한 의미가 없습니다.  따라서 첫 번째 구문을 사용하는 주석은 중첩할 수 없습니다.  
  
## 참고 항목  
 [어휘 규칙](../cpp/lexical-conventions.md)