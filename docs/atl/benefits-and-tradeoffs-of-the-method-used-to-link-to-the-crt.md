---
title: "Benefits and Tradeoffs of the Method Used to Link to the CRT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MIN_CRT 매크로"
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Benefits and Tradeoffs of the Method Used to Link to the CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트는 CRT에 동적으로 또는 정적으로 연결할 수 있습니다.  아래 표에서 장점과 사용 방법 선택에 관련 된 장단점에 설명 합니다.  
  
|메서드|혜택|상충 관계|  
|---------|--------|-----------|  
|CRT에 정적 링크<br /><br /> \(**런타임 라이브러리** 설정  **단일 스레드**\)|이미지가 실행 됩니다 시스템에 CRT DLL 필요 하지 않습니다.|약 25k의 시작 코드 크기를 크게 늘리지 이미지에 추가 됩니다.|  
|CRT에 동적으로 연결<br /><br /> \(**런타임 라이브러리** 설정  **다중 스레드**\)|이므로 훨씬 작은 이미지에 CRT 시작 코드가 필요 하지 않습니다.|CRT DLL 이미지를 실행 하는 시스템에 있어야 합니다.|  
  
 항목  [ATL 프로젝트에서 CRT에 링크](../atl/linking-to-the-crt-in-your-atl-project.md) CRT에 링크 하는 방식을 선택 하는 방법에 설명 합니다.  
  
## 참고 항목  
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../atl/programming-with-atl-and-c-run-time-code.md)   
 [런타임 라이브러리 동작](../build/run-time-library-behavior.md)   
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)