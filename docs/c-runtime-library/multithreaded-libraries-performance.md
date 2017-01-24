---
title: "다중 스레드 라이브러리 성능 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "라이브러리, 다중 스레드"
  - "다중 스레드 라이브러리"
  - "성능, 다중 스레딩"
  - "스레딩[C++], 성능"
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 다중 스레드 라이브러리 성능
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단일 스레드 CRT를 사용할 수 없습니다.  이 항목에는 다중 스레드 라이브러리에서 최대 성능을 얻는 방법을 설명 합니다.  
  
## 성능 최적화  
 다중 스레드 라이브러리 성능 개선 되었으며 이제 제거 단일 스레드 라이브러리의 성능에 근접 합니다.  이러한 경우 더 높은 성능을 위해, 필요한 몇 가지 새 기능이 있습니다.  
  
-   독립적인 스트림의 잠금은 스트림을 고정하여 사용하여 [\_nolock 함수](../c-runtime-library/nolock-functions.md) 스트림에 직접 액세스 합니다.  잠금 사용을에 중요한 루프 외부에서 가져온 수 있습니다.  
  
-   스레드별 로캘을 로캘 액세스 다중 스레드 시나리오에 대한 비용을 줄일 수 있습니다.\(참조 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)\).  
  
-   로캘 종속 함수는 \(\_l으로 끝나는 이름\) 변수로서 로캘을 취합니다, 실질적인 비용 제거합니다. \(예를 들어, [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\).  
  
-   일반 코드 페이지에 대한 최적화는 짧은 작업 비용을 절감 합니다.  
  
-   이 [\_CRT\_DISABLE\_PERFCRIT\_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) 를 정의하는 것은 모든 I\/O 작업이 단일 스레드 I\/O 모델을 측정하고 \_nolock 형태인 함수를 사용하는 것을 강요합니다.  따라서 높은 I\/O 단일 스레드 응용 프로그램 성능을 향상 시킬 수 있습니다.  
  
-   CRT 힘 처리기의 노출은 Windows의 낮은 조각화 힙\(LFH\)이 CRT 힙을 위한 자격을 주는 것을 허용합니다, 높은 배율이 지정된 시나리오에서 이는 나중에 성능을 개선시킬 수 있습니다.  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)