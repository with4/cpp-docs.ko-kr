---
title: "Date and Time: Automation Support | Microsoft Docs"
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
  - "자동화, date and time support"
  - "calculating dates and times"
  - "계산, 날짜 및 시간"
  - "COleDateTime class, Automation date/time support"
  - "COleDateTimeSpan class, Automation date/time support"
  - "날짜, Automation support"
  - "경과 시간, calculating in Automation"
  - "서식 지정[Visual Studio], 날짜"
  - "서식 지정[Visual Studio], 시간"
  - "시간[Visual Studio], Automation support"
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Date and Time: Automation Support
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 날짜 및 시간 관리와 관련 된 클래스 라이브러리 서비스를 활용 하는 방법을 설명 합니다.  설명 하는 절차는 다음과 같습니다.  
  
-   [현재 시간을 가져오는 중](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [경과 된 시간 계산](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [나타내는 문자열을 날짜\/시간 서식](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) 클래스는 날짜 및 시간 정보를 표시 하는 방법을 제공 합니다.  세밀 하 고 보다 넓은 범위에 제공 된  [CTime](../atl-mfc-shared/reference/ctime-class.md) 클래스입니다.  [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) 클래스는 두 경과 시간을 나타내는 `COleDateTime` 개체입니다.  
  
 `COleDateTime` 및 `COleDateTimeSpan` 클래스에 사용 되도록 설계는 `COleVariant` 클래스에서 자동화를 사용 합니다.  `COleDateTime`및 `COleDateTimeSpan` MFC 데이터베이스 프로그래밍에도 유용 하지만 원하는 날짜 및 시간 값을 다룰 때마다 사용할 수 있습니다.  하지만 `COleDateTime` 클래스에 보다 세밀 한 값의 범위는 `CTime` 클래스에 필요한 개체 보다 더 많은 스토리지 `CTime`.  또한 몇 가지 특별히 고려할 사항은 기본으로 작업 하는 경우  **날짜** 형식입니다.  참조  [DATE 형식](../atl-mfc-shared/date-type.md) 구현에 대 한 자세한 내용은  **날짜**.  
  
 `COleDateTime`개체는 9999 100 년 1 월 1 일 및 12 월 31 일 사이의 날짜를 나타내는 데 사용할 수 있습니다.  `COleDateTime`개체 부동 소수점 값은 대략적인 해상도 1 밀리초의.  `COleDateTime`기반이 되는  **날짜** MFC 설명서에서 정의 하는 데이터 형식  [COleDateTime::operator 날짜](../Topic/COleDateTime::operator%20DATE.md).  실제 구현의  **날짜** 이러한 경계를 벗어나 확장 합니다.  `COleDateTime` 구현 클래스가 작업을 용이 하 게 이러한 경계를 적용 합니다.  
  
 `COleDateTime`율리우스 날짜를 지원 하지 않습니다.  그레고리오 력 100 년 1 월 1 일 날짜로 확장으로 간주 됩니다.  
  
 `COleDateTime`일광 절약 시간제 \(DST\)를 무시합니다.  다음 코드 예제에서는 DST 전환 날짜는 기간 계산의 두 가지 방법을 비교: 하나는 CRT를 사용 하 고 다른 using `COleDateTime`.  DST를 통해 세 번째 10 월에서 및 4 월에서 둘째 주에 전환합니다.  
  
 설정 하는 첫 번째 방법은 두 `CTime` 개체  *time1* 및  *time2와*, 4 월 5\-6 월에 각각 표준 C 형식 구조를 사용 하 여  **tm** 및 `time_t`.  코드 표시  *time1* 및  *time2와* 및 이들 사이의 기간.  
  
 두 번째 메서드를 만듭니다 `COleDateTime` 개체 `oletime1` 및 `oletime2`,이 같은 날짜로 설정 하 고  *time1* 및  *time2와*.  표시 `oletime1` 및 `oletime2` 및 이들 사이의 기간.  
  
 CRT 제대로 23 시간 차이 계산합니다.  `COleDateTimeSpan`24 시간의 차이 계산합니다.  
  
 해결 방법을 제대로 사용 하 여 날짜를 표시 하려면 사용 예제 끝날 무렵 `COleDateTime::Format`.  기술 자료 문서 "버그: Format\("%D"\) 실패에 대 한 `COleDateTime` 및 `COleDateTimeSpan`" \(Q167338\).  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/CPP/date-and-time-automation-support_1.cpp)]  
  
## 참고 항목  
 [Date and Time](../atl-mfc-shared/date-and-time.md)