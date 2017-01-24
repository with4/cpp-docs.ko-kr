---
title: "Elapsed Time: General-Purpose Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adding dates"
  - "calculating dates and times"
  - "계산, 날짜 및 시간"
  - "날짜, calculating intervals"
  - "경과 시간"
  - "경과 시간, 계산"
  - "intervals, 날짜 및 시간"
  - "시간, elapsed"
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Elapsed Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 프로시저 2 간의 차이 계산 하는 방법을 보여 줍니다. `CTime` get 및 개체는 `CTimeSpan` 결과.  
  
#### 경과 시간을 계산.  
  
1.  사용 된 `CTime` 및 `CTimeSpan` 같이 경과 시간을 계산 하는 개체:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/CPP/elapsed-time-general-purpose-classes_1.cpp)]  
  
     계산 된 후 `elapsedTime`의 멤버 함수를 사용할 수 있습니다 `CTimeSpan` 경과 시간 값은 구성 요소를 추출 합니다.  
  
## 참고 항목  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)