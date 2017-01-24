---
title: "COleDateTimeSpan Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.COleDateTimeSpan"
  - "COleDateTimeSpan"
  - "ATL::COleDateTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTimeSpan class"
  - "Date 데이터 형식, MFC encapsulation of"
  - "shared classes, COleDateTimeSpan"
  - "time span"
  - "timespan"
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: 19
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDateTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상대 시간을 시간 범위를 나타냅니다.  
  
## 구문  
  
```  
class COleDateTimeSpan  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDateTimeSpan::COleDateTimeSpan](../Topic/COleDateTimeSpan::COleDateTimeSpan.md)|`COleDateTimeSpan` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDateTimeSpan::Format](../Topic/COleDateTimeSpan::Format.md)|서식이 지정 된 문자열을 생성 하는 `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::GetDays](../Topic/COleDateTimeSpan::GetDays.md)|두 일 부분을 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::GetHours](../Topic/COleDateTimeSpan::GetHours.md)|이 범위는 시간 부분을 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::GetMinutes](../Topic/COleDateTimeSpan::GetMinutes.md)|이 분 부분 범위를 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::GetSeconds](../Topic/COleDateTimeSpan::GetSeconds.md)|이 범위를 두 번째 부분을 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::GetStatus](../Topic/COleDateTimeSpan::GetStatus.md)|이 상태 \(유효\) 가져옵니다 `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::GetTotalDays](../Topic/COleDateTimeSpan::GetTotalDays.md)|이 일 수를 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::GetTotalHours](../Topic/COleDateTimeSpan::GetTotalHours.md)|이 시간을 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::GetTotalMinutes](../Topic/COleDateTimeSpan::GetTotalMinutes.md)|분이 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::GetTotalSeconds](../Topic/COleDateTimeSpan::GetTotalSeconds.md)|초가 반환 `COleDateTimeSpan` 개체를 나타냅니다.|  
|[COleDateTimeSpan::SetDateTimeSpan](../Topic/COleDateTimeSpan::SetDateTimeSpan.md)|이 값은 설정 `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::SetStatus](../Topic/COleDateTimeSpan::SetStatus.md)|설정 상태 \(유효\)이 `COleDateTimeSpan` 개체입니다.|  
  
### Public 연산자  
  
|||  
|-|-|  
|[연산자 \+,\-](../Topic/COleDateTimeSpan::operator%20+,%20-.md)|추가, 빼기, 및 기호에 대 한 변경 `COleDateTimeSpan` 값입니다.|  
|[연산자 \+ \=, \=](../Topic/COleDateTimeSpan::operator%20+=,%20-=.md)|더하기 및 빼기를 `COleDateTimeSpan` 값이 `COleDateTimeSpan` 값입니다.|  
|[연산자 \=](../Topic/COleDateTimeSpan::operator%20=.md)|복사본은 `COleDateTimeSpan` 값입니다.|  
|[연산자: \= \=, \<, \< \=](../Topic/COleDateTimeSpan%20Relational%20Operators.md)|두 비교 `COleDateTimeSpan` 값입니다.|  
|[이중 연산자](../Topic/COleDateTimeSpan::operator%20double.md)|이 변환 `COleDateTimeSpan` 값은  **이중**.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleDateTimeSpan::m\_span](../Topic/COleDateTimeSpan::m_span.md)|기본 포함  **이중** 이 `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::m\_status](../Topic/COleDateTimeSpan::m_status.md)|이 상태를 포함 `COleDateTimeSpan` 개체입니다.|  
  
## 설명  
 `COleDateTimeSpan`기본 클래스에 없는 것입니다.  
  
 A `COleDateTimeSpan` 일에 시간을 유지 합니다.  
  
 `COleDateTimeSpan`해당 도우미 클래스와 함께 사용 되어  [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).  `COleDateTime`캡슐화는  **날짜** OLE 자동화 데이터 형식입니다.  `COleDateTime`절대 시간 값을 나타냅니다.  모든 `COleDateTime` 계산 포함 `COleDateTimeSpan` 값입니다.  이러한 클래스 간의 관계는 사이 유사  [CTime](../../atl-mfc-shared/reference/ctime-class.md) 및  [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 에 대 한 자세한 내용은 `COleDateTime` 및 `COleDateTimeSpan` 클래스, 문서를 참고 하십시오.  [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## 요구 사항  
 **헤더:**  ATLComTime.h  
  
## 참고 항목  
 [COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime Class](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)