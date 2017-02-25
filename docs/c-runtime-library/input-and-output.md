---
title: "입력 및 출력 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "I/O[CRT]"
  - "I/O[CRT], 루틴"
  - "I/O 루틴"
  - "입력 루틴"
  - "출력 루틴"
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 입력 및 출력
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

I\/O 함수는 파일 및 장치에 데이터를 쓰고 읽습니다.  텍스트 모드 또는 이진 모드로 파일 I\/O 작업을 수행 합니다.  Microsoft 런타임 라이브러리는 세 가지 유형의 I\/O 함수를 가지고 있습니다.  
  
-   [Stream I\/O](../c-runtime-library/stream-i-o.md) 함수는 데이터를 데이터를 개별 적인 문자의 스트림으로 처리합니다.  
  
-   [Low\-level I\/O](../c-runtime-library/low-level-i-o.md) 함수는 스트림 I\/O가 제공하는 것보다 낮은 수준의 운영 체제를 직접적으로 호출합니다.  
  
-   [Console and port I\/O](../c-runtime-library/console-and-port-i-o.md) 함수는 콘솔\(키보드 및 화면\) 또는 I\/O 포트에 직접적으로 읽거나 씁니다.  
  
    > [!NOTE]
    >  스트림 함수는 버퍼링 된 함수이고 낮은 수준의 함수는 아니기 때문에 함수의 두 유형은 일반적으로 호환성이 없습니다.  특정 파일 처리를 위해 단독으로 스트림 또는 하위 수준 기능을 사용 합니다.  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)