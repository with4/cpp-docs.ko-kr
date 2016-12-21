---
title: "Date and Time: General-Purpose Classes | Microsoft Docs"
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
  - "date and time classes"
  - "time classes"
ms.assetid: b8115d7f-428a-4c41-9970-18502f2caca2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Date and Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 날짜 및 시간 관리와 관련 된 일반적인 서비스 클래스 라이브러리를 활용 하는 방법을 설명 합니다.  설명 하는 절차는 다음과 같습니다.  
  
-   [현재 시간을 가져오는 중](../atl-mfc-shared/current-time-general-purpose-classes.md)  
  
-   [경과 된 시간 계산](../atl-mfc-shared/elapsed-time-general-purpose-classes.md)  
  
-   [나타내는 문자열을 날짜\/시간 서식](../atl-mfc-shared/formatting-time-values-general-purpose-classes.md)  
  
 `CTime` 클래스 정보를 쉽게 시간 날짜를 표시 하는 방법을 제공 합니다.  `CTimeSpan` 클래스는 두 경과 시간을 나타내는 `CTime` 개체입니다.  
  
> [!NOTE]
>  CTime 개체 1970 년 1 월 1 일 2038 년 1 월 18 일 사이의 날짜를 나타내는 데 사용할 수 있습니다.  `CTime`개체를 1 초 해상도 있습니다.  `CTime`기준으로 `time_t` 데이터 형식 정의  *런타임 라이브러리 참조*.  
  
## 참고 항목  
 [Date and Time](../atl-mfc-shared/date-and-time.md)