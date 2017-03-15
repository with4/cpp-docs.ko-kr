---
title: "Elapsed Time: Automation Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "Automation classes, 경과 시간"
  - "calculating dates and times"
  - "계산, 날짜 및 시간"
  - "날짜, calculating intervals"
  - "경과 시간, calculating in Automation"
  - "intervals, 날짜 및 시간"
  - "시간, elapsed"
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Elapsed Time: Automation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 프로시저 두 간의 차이 계산 하는 방법을 보여 줍니다. `CTime` get 및 개체는 `CTimeSpan` 결과.  
  
#### 경과 시간을 계산.  
  
1.  두 개의 `COleDateTime` 개체입니다.  
  
2.  설정 중 하나는 `COleDateTime` 개체의 현재 시간입니다.  
  
3.  시간이 걸리는 작업을 수행 합니다.  
  
4.  다른 설정 `COleDateTime` 개체의 현재 시간입니다.  
  
5.  두 시간 사이의 차이 사용 합니다.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/CPP/elapsed-time-automation-classes_1.cpp)]  
  
## 참고 항목  
 [Date and Time: Automation Support](../atl-mfc-shared/date-and-time-automation-support.md)