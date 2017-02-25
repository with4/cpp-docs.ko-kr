---
title: "COleDateTime Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDateTime"
  - "ATL.COleDateTime"
  - "ATL::COleDateTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTime class"
  - "Date 데이터 형식, MFC encapsulation of"
  - "날짜, handling in MFC"
  - "shared classes, COleDateTime"
  - "시간, handling in MFC"
  - "time-only values"
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# COleDateTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

캡슐화 된 `DATE` OLE 자동화를 사용 하는 데이터 형식입니다.  
  
## 구문  
  
```  
class COleDateTime  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[COleDateTime::COleDateTime](../Topic/COleDateTime::COleDateTime.md)|`COleDateTime` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[COleDateTime::Format](../Topic/COleDateTime::Format.md)|서식이 지정 된 문자열 표현을 생성 하는 `COleDateTime` 개체입니다.|  
|[COleDateTime::GetAsDBTIMESTAMP](../Topic/COleDateTime::GetAsDBTIMESTAMP.md)|시간을 가져오려면이 메서드를 호출 하는 `COleDateTime` 개체는  **DBTIMESTAMP** 데이터 구조입니다.|  
|[COleDateTime::GetAsSystemTime](../Topic/COleDateTime::GetAsSystemTime.md)|시간을 가져오려면이 메서드를 호출 하는 `COleDateTime` 개체는  [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 데이터 구조입니다.|  
|[COleDateTime::GetAsUDATE](../Topic/COleDateTime::GetAsUDATE.md)|시간을 가져오려면이 메서드를 호출 하는 `COleDateTime` 로  **UDATE** 데이터 구조입니다.|  
|[COleDateTime::GetCurrentTime](../Topic/COleDateTime::GetCurrentTime.md)|만들고는 `COleDateTime` \(정적 멤버 함수\) 현재 시간을 나타내는 개체입니다.|  
|[COleDateTime::GetDay](../Topic/COleDateTime::GetDay.md)|일이 반환 `COleDateTime` 개체 \(1 – 31\)를 나타냅니다.|  
|[COleDateTime::GetDayOfWeek](../Topic/COleDateTime::GetDayOfWeek.md)|특정 요일을 반환 `COleDateTime` 개체가 나타내는 \(일요일 \= 1\).|  
|[COleDateTime::GetDayOfYear](../Topic/COleDateTime::GetDayOfYear.md)|일 년이 반환 `COleDateTime` 개체가 나타내는 \(01 \= 1\).|  
|[COleDateTime::GetHour](../Topic/COleDateTime::GetHour.md)|반환 시 `COleDateTime` 개체가 나타내는 \(0\-23\).|  
|[COleDateTime::GetMinute](../Topic/COleDateTime::GetMinute.md)|이 분을 반환 `COleDateTime` 개체가 나타내는 \(0\-59\).|  
|[COleDateTime::GetMonth](../Topic/COleDateTime::GetMonth.md)|월 반환 `COleDateTime` 개체를 나타냅니다 \(1\-12\).|  
|[COleDateTime::GetSecond](../Topic/COleDateTime::GetSecond.md)|이 두 번째 반환 `COleDateTime` 개체가 나타내는 \(0\-59\).|  
|[COleDateTime::GetStatus](../Topic/COleDateTime::GetStatus.md)|이 상태 \(유효\) 가져옵니다 `COleDateTime` 개체입니다.|  
|[COleDateTime::GetYear](../Topic/COleDateTime::GetYear.md)|연도 반환 `COleDateTime` 개체를 나타냅니다.|  
|[COleDateTime::ParseDateTime](../Topic/COleDateTime::ParseDateTime.md)|문자열에서 날짜\/시간 값을 읽고 값을 설정 `COleDateTime`.|  
|[COleDateTime::SetDate](../Topic/COleDateTime::SetDate.md)|이 값은 설정 하는 `COleDateTime` 개체를 지정 된 날짜만 값.|  
|[COleDateTime::SetDateTime](../Topic/COleDateTime::SetDateTime.md)|이 값은 설정 하는 `COleDateTime` 개체를 지정 된 날짜\/시간 값입니다.|  
|[COleDateTime::SetStatus](../Topic/COleDateTime::SetStatus.md)|이 상태 \(유효\) 설정 하는 `COleDateTime` 개체입니다.|  
|[COleDateTime::SetTime](../Topic/COleDateTime::SetTime.md)|이 값은 설정 하는 `COleDateTime` 전용 시간으로 지정 된 값 개체입니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[COleDateTime::operator \= \= COleDateTime::operator \< 등.](../Topic/COleDateTime%20Relational%20Operators.md)|두 `COleDateTime` 값입니다.|  
|[COleDateTime::operator \+, COleDateTime::operator\-](../Topic/COleDateTime::operator%20+,%20-.md)|더하기 및 빼기를 `COleDateTime` 값입니다.|  
|[COleDateTime::operator \+, COleDateTime::operator \= \=](../Topic/COleDateTime::operator%20+=,%20-=.md)|더하기 및 빼기를 `COleDateTime` 값이 `COleDateTime` 개체입니다.|  
|[COleDateTime::operator \=](../Topic/COleDateTime::operator%20=.md)|복사본을 `COleDateTime` 값입니다.|  
|[COleDateTime::operator 날짜 COleDateTime::operator 날짜 \*](../Topic/COleDateTime::operator%20DATE.md)|Converts a `COleDateTime` value into a `DATE` or a `DATE*`.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[COleDateTime::m\_dt](../Topic/COleDateTime::m_dt.md)|내부에 포함 된  **날짜** 이 `COleDateTime` 개체입니다.|  
|[COleDateTime::m\_status](../Topic/COleDateTime::m_status.md)|이 상태가 포함 된 `COleDateTime` 개체입니다.|  
  
## 설명  
 `COleDateTime`기본 클래스가 없습니다.  
  
 가능한 형식 중 하나입니다에  [변형](http://msdn.microsoft.com/ko-kr/e305240e-9e11-4006-98cc-26f4932d2118) OLE 자동화 데이터 형식이 있습니다.  A `COleDateTime` 값 절대 날짜 및 시간 값을 나타냅니다.  
  
 `DATE` 형식의 부동 소수점 값으로 구현 됩니다.  일, 1899 년 12 월 30 일에서 자정 까지입니다.  다음 표에 일부 날짜와 관련 된 값을 보여 줍니다.  
  
|날짜|값|  
|--------|-------|  
|1899 년 12 월 29 일 자정|\-1.0|  
|1899 년 12 월 29 일, 오전 6|\-1.25|  
|1899 년 12 월 30 일 자정|0.0|  
|1899 년 12 월 31 일 자정|1.0|  
|1900 년 1 월 1 일 6 A.M.|2.25|  
  
> [!CAUTION]
>  위의 표에 자정 이전에 1899 년 12 월 30 일 값 음수 됩니다 있지만 일일 시간 값 않습니다 있는지 note입니다.  예를 들어 오전 6 시 소수 값 0.25 일을 나타내는 정수 \(1899 년 12 월 30 일\) 후 양수 또는 음수 \(1899 년 12 월 30 일\) 이전 여부에 관계 없이 항상 표시 됩니다.  즉 단순한 부동 소수점 비교 잘못 정렬 되는 `COleDateTime` 1899 년 12 월 29 일으로 오전 6시 나타내는  **나중에** 보다 하나를 나타내는 같은 날 오전 7시.  
  
 `COleDateTime` 클래스는 9999 1 100 년 1 월, 12 월 31 일에서 날짜를 처리 합니다.  `COleDateTime` 클래스를 사용 하는 그레고리오 력; 율리우스 날짜는 지원 하지 않습니다.  `COleDateTime`일광 절약 시간을 무시합니다.  \(참조 하십시오  [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md).\)  
  
> [!NOTE]
>  사용할 수 있는 `%y` 는 1900에서 시작 하는 날짜를 두 자리 연도 검색 하려면 서식을.  사용 하는 경우는 `%y` 형식 코드 1900 년 이전 날짜에 어설션 실패 오류가 생성 됩니다.  
  
 이 형식은 또한 날짜 전용 이나 시간 값을 나타내는 데 사용 됩니다.  규칙, 날짜 \(1899 년 12 월 30 일\) 0 번만 값을 사용 하 고 날짜 전용 값에는 시간 00: 00 \(자정\) 사용 됩니다.  
  
 만들 경우는 `COleDateTime` 날짜를 사용 하 여 개체 미만 100 날짜 허용, 하지만 후속 호출 될 `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, 및 `GetSecond` 실패 하 고\-1을 반환 합니다.  이전에 두 자리 날짜를 사용할 수 있지만 100 또는 MFC 4.2에서 크고 이후 날짜 여야 합니다.  
  
 문제를 피하려면 네 자리 날짜를 지정 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/CPP/coledatetime-class_1.cpp)]  
  
 기본적인 산술 연산에는 `COleDateTime` 값을 사용 하는 도우미 클래스  [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md).  `COleDateTimeSpan`값은 시간 간격을 정의합니다.  이들이 클래스 간의 관계 간의 유사  [CTime](../../atl-mfc-shared/reference/ctime-class.md) 및  [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 에 대 한 자세한 내용은 `COleDateTime` 및 `COleDateTimeSpan` 클래스 문서를 참조 하십시오  [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## 요구 사항  
 **헤더:** ATLComTime.h  
  
## 참고 항목  
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CTime Class](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)