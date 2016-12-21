---
title: "CTimeSpan Class | Microsoft Docs"
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
  - "ATL.CTimeSpan"
  - "CTimeSpan"
  - "timespan"
  - "ATL::CTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTimeSpan class"
  - "경과 시간, CTimeSpan object"
  - "shared classes, CTimeSpan"
  - "time span"
  - "시간, elapsed"
  - "timespan"
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간 범위의 초 수로 내부적으로 저장 하는 시간 양입니다.  
  
## 구문  
  
```  
class CTimeSpan  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CTimeSpan::CTimeSpan](../Topic/CTimeSpan::CTimeSpan.md)|생성 `CTimeSpan` 개체에서 다양 한 방법으로.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTimeSpan::Format](../Topic/CTimeSpan::Format.md)|변환 된 `CTimeSpan` 를 서식이 지정 된 문자열.|  
|[CTimeSpan::GetDays](../Topic/CTimeSpan::GetDays.md)|두 일 수를 나타내는 값을 반환 합니다. `CTimeSpan`.|  
|[CTimeSpan::GetHours](../Topic/CTimeSpan::GetHours.md)|현재 \(–23부터 23\) 일에 시간을 나타내는 값을 반환 합니다.|  
|[CTimeSpan::GetMinutes](../Topic/CTimeSpan::GetMinutes.md)|현재 시간 \(–59\-59\) 분 수를 나타내는 값을 반환 합니다.|  
|[CTimeSpan::GetSeconds](../Topic/CTimeSpan::GetSeconds.md)|현재 분 \(–59\-59\) 초 수를 나타내는 값을 반환 합니다.|  
|[CTimeSpan::GetTimeSpan](../Topic/CTimeSpan::GetTimeSpan.md)|`CTimeSpan` 개체의 값을 반환합니다.|  
|[CTimeSpan::GetTotalHours](../Topic/CTimeSpan::GetTotalHours.md)|총이 완료 시간을 나타내는 값을 반환 합니다. `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](../Topic/CTimeSpan::GetTotalMinutes.md)|이 분의 총 수를 나타내는 값을 반환 합니다. `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](../Topic/CTimeSpan::GetTotalSeconds.md)|전체 시간 \(초\)이 총 수를 나타내는 값을 반환 합니다. `CTimeSpan`.|  
|[CTimeSpan::Serialize64](../Topic/CTimeSpan::Serialize64.md)|보관 파일에서 데이터를 serialize합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \+\-](../Topic/CTimeSpan::operator%20+,%20-.md)|추가 하 고 빼는 `CTimeSpan` 개체입니다.|  
|[연산자 \+ \= \=](../Topic/CTimeSpan::operator%20+=,%20-=.md)|추가 하 고 빼는 `CTimeSpan` 개체와이 `CTimeSpan`.|  
|[연산자 \= \= \< 등.](../Topic/CTimeSpan%20Comparison%20Operators.md)|두 상대 시간 값을 비교합니다.|  
  
## 설명  
 `CTimeSpan`기본 클래스에 없는 것입니다.  
  
 `CTimeSpan`함수에 여러 가지로 조합해 일, 시간, 분, 초 및 초 변환합니다.  
  
 `CTimeSpan` 개체에 저장 되는  **\_\_time64\_t** 구조를 8 바이트입니다.  
  
 도우미 클래스를  [CTime](../../atl-mfc-shared/reference/ctime-class.md), 절대 시간을 나타냅니다.  
  
 `CTime` 및 `CTimeSpan` 클래스 파생에 대 한 설계 되지 않았습니다.  가상 함수가 없는, 둘 다의 크기 때문에 `CTime` 및 `CTimeSpan` 개체는 정확히 8 바이트입니다.  대부분의 멤버 함수를 인라인 됩니다.  
  
 사용에 대 한 자세한 내용은 `CTimeSpan`, 문서를 참고 하십시오  [날짜와 시간](../../atl-mfc-shared/date-and-time.md), 및  [시간 관리](../../c-runtime-library/time-management.md) 에 있는  *런타임 라이브러리 참조*.  
  
## 요구 사항  
 **헤더:**  atltime.h  
  
## 참고 항목  
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)