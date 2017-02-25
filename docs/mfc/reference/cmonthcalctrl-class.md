---
title: "CMonthCalCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMonthCalCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl class"
  - "공용 컨트롤, Internet Explorer 4.0"
  - "Internet Explorer 4.0 common controls"
  - "month calendar controls"
  - "month calendar controls, CMonthCalCtrl class"
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMonthCalCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Month calendar 컨트롤의 기능을 캡슐화합니다.  
  
## 구문  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMonthCalCtrl::CMonthCalCtrl](../Topic/CMonthCalCtrl::CMonthCalCtrl.md)|`CMonthCalCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMonthCalCtrl::Create](../Topic/CMonthCalCtrl::Create.md)|Month calendar 컨트롤을 만들고이에 연결 된 `CMonthCalCtrl` 개체입니다.|  
|[CMonthCalCtrl::GetCalendarBorder](../Topic/CMonthCalCtrl::GetCalendarBorder.md)|현재 month calendar 컨트롤의 테두리 너비를 검색합니다.|  
|[CMonthCalCtrl::GetCalendarCount](../Topic/CMonthCalCtrl::GetCalendarCount.md)|현재 달 달력 컨트롤에 표시 되는 달력을 검색 합니다.|  
|[CMonthCalCtrl::GetCalendarGridInfo](../Topic/CMonthCalCtrl::GetCalendarGridInfo.md)|현재 컨트롤에 대 한 정보를 검색합니다.|  
|[CMonthCalCtrl::GetCalID](../Topic/CMonthCalCtrl::GetCalID.md)|현재 month calendar 컨트롤에 대 한 일정 식별자를 검색합니다.|  
|[CMonthCalCtrl::GetColor](../Topic/CMonthCalCtrl::GetColor.md)|Month calendar 컨트롤의 지정 된 영역의 색을 가져옵니다.|  
|[CMonthCalCtrl::GetCurrentView](../Topic/CMonthCalCtrl::GetCurrentView.md)|현재 달 달력 컨트롤에서 현재 표시 되는 보기를 검색 합니다.|  
|[CMonthCalCtrl::GetCurSel](../Topic/CMonthCalCtrl::GetCurSel.md)|현재 선택한 날짜를 기준으로 지정 된 시스템 시간을 검색 합니다.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](../Topic/CMonthCalCtrl::GetFirstDayOfWeek.md)|첫째 날을 달력의 맨 왼쪽 열에 표시할 요일을 가져옵니다.|  
|[CMonthCalCtrl::GetMaxSelCount](../Topic/CMonthCalCtrl::GetMaxSelCount.md)|Month calendar 컨트롤에서 선택할 수 있습니다 일 현재 최대 개수를 검색 합니다.|  
|[CMonthCalCtrl::GetMaxTodayWidth](../Topic/CMonthCalCtrl::GetMaxTodayWidth.md)|현재 month calendar 컨트롤의 "오늘" 문자열의 최대 너비를 검색합니다.|  
|[CMonthCalCtrl::GetMinReqRect](../Topic/CMonthCalCtrl::GetMinReqRect.md)|달 month calendar 컨트롤에 표시 하는 데 필요한 최소 크기를 검색 합니다.|  
|[CMonthCalCtrl::GetMonthDelta](../Topic/CMonthCalCtrl::GetMonthDelta.md)|Month calendar 컨트롤의 스크롤 속도 검색합니다.|  
|[CMonthCalCtrl::GetMonthRange](../Topic/CMonthCalCtrl::GetMonthRange.md)|검색 정보 높고 낮은 한계 month calendar 컨트롤의 표시를 나타내는 날짜입니다.|  
|[CMonthCalCtrl::GetRange](../Topic/CMonthCalCtrl::GetRange.md)|Month calendar 컨트롤에 설정 현재 최소 및 최대 날짜를 검색 합니다.|  
|[CMonthCalCtrl::GetSelRange](../Topic/CMonthCalCtrl::GetSelRange.md)|현재 사용자가 선택한 날짜 범위의 최소값 및 최대값을 나타내는 날짜 정보를 검색 합니다.|  
|[CMonthCalCtrl::GetToday](../Topic/CMonthCalCtrl::GetToday.md)|Month calendar 컨트롤의 "오늘"로 지정 된 날짜의 날짜 정보를 검색 합니다.|  
|[CMonthCalCtrl::HitTest](../Topic/CMonthCalCtrl::HitTest.md)|화면의 지정 된 지점에서 month calendar 컨트롤의 어느 부분 인지 확인 합니다.|  
|[CMonthCalCtrl::IsCenturyView](../Topic/CMonthCalCtrl::IsCenturyView.md)|현재 보기 현재 month calendar 컨트롤의 세기 보기 인지 여부를 나타냅니다.|  
|[CMonthCalCtrl::IsDecadeView](../Topic/CMonthCalCtrl::IsDecadeView.md)|현재 보기 현재 month calendar 컨트롤의 10 년 보기 인지 여부를 나타냅니다.|  
|[CMonthCalCtrl::IsMonthView](../Topic/CMonthCalCtrl::IsMonthView.md)|현재 보기 현재 month calendar 컨트롤의 월 보기 인지 여부를 나타냅니다.|  
|[CMonthCalCtrl::IsYearView](../Topic/CMonthCalCtrl::IsYearView.md)|현재 보기 현재 month calendar 컨트롤의 연도 보기 인지 여부를 나타냅니다.|  
|[CMonthCalCtrl::SetCalendarBorder](../Topic/CMonthCalCtrl::SetCalendarBorder.md)|현재 month calendar 컨트롤의 테두리 너비를 설정합니다.|  
|[CMonthCalCtrl::SetCalendarBorderDefault](../Topic/CMonthCalCtrl::SetCalendarBorderDefault.md)|현재 month calendar 컨트롤의 테두리의 기본 너비를 설정합니다.|  
|[CMonthCalCtrl::SetCalID](../Topic/CMonthCalCtrl::SetCalID.md)|현재 month calendar 컨트롤에 대 한 일정 식별자를 설정합니다.|  
|[CMonthCalCtrl::SetCenturyView](../Topic/CMonthCalCtrl::SetCenturyView.md)|세기 표시를 현재 월 달력 컨트롤을 설정 합니다.|  
|[CMonthCalCtrl::SetColor](../Topic/CMonthCalCtrl::SetColor.md)|Month calendar 컨트롤의 지정 된 영역의 색상을 설정합니다.|  
|[CMonthCalCtrl::SetCurrentView](../Topic/CMonthCalCtrl::SetCurrentView.md)|지정 된 보기를 표시 하려면 현재 달 달력 컨트롤을 설정 합니다.|  
|[CMonthCalCtrl::SetCurSel](../Topic/CMonthCalCtrl::SetCurSel.md)|Month calendar 컨트롤에 현재 선택된 된 날짜를 설정합니다.|  
|[CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md)|Month calendar 컨트롤에서 일에 대 한 표시를 설정합니다.|  
|[CMonthCalCtrl::SetDecadeView](../Topic/CMonthCalCtrl::SetDecadeView.md)|현재 달력 세트 10 년 보기를 제어 합니다.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](../Topic/CMonthCalCtrl::SetFirstDayOfWeek.md)|달력의 맨 왼쪽 열에 표시할 요일을 설정 합니다.|  
|[CMonthCalCtrl::SetMaxSelCount](../Topic/CMonthCalCtrl::SetMaxSelCount.md)|Month calendar 컨트롤에서 선택할 수 있는 일 수를 설정 합니다.|  
|[CMonthCalCtrl::SetMonthDelta](../Topic/CMonthCalCtrl::SetMonthDelta.md)|Month calendar 컨트롤의 스크롤 속도 설정합니다.|  
|[CMonthCalCtrl::SetMonthView](../Topic/CMonthCalCtrl::SetMonthView.md)|월 보기를 표시 하려면 현재 달 달력 컨트롤을 설정 합니다.|  
|[CMonthCalCtrl::SetRange](../Topic/CMonthCalCtrl::SetRange.md)|최소 및 최대 허용 month calendar 컨트롤의 날짜를 설정 합니다.|  
|[CMonthCalCtrl::SetSelRange](../Topic/CMonthCalCtrl::SetSelRange.md)|설정 선택 월 일정에 지정 된 날짜 범위를 제어 합니다.|  
|[CMonthCalCtrl::SetToday](../Topic/CMonthCalCtrl::SetToday.md)|Calendar 컨트롤에 현재 날짜를 설정합니다.|  
|[CMonthCalCtrl::SetYearView](../Topic/CMonthCalCtrl::SetYearView.md)|설정 현재 달력 연도 보기를 제어 합니다.|  
|[CMonthCalCtrl::SizeMinReq](../Topic/CMonthCalCtrl::SizeMinReq.md)|달력 다시 최소, 한 달에 크기를 제어 합니다.|  
|[CMonthCalCtrl::SizeRectToMin](../Topic/CMonthCalCtrl::SizeRectToMin.md)|현재 달 달력 컨트롤을 지정 된 사각형에 맞게 모든 일정을 포함할 수 있는 가장 작은 사각형을 계산 합니다.|  
  
## 설명  
 Month calendar 컨트롤을 사용자가 날짜를 선택할 수 있는 간단한 달력 인터페이스와 사용자를 제공 합니다.  사용자가 디스플레이 변경할 수 있습니다.  
  
-   뒤로 스크롤 및 앞으로 달 달 합니다.  
  
-   오늘 현재 날짜를 표시 하려면 텍스트를 클릭 하면 \(경우에  **MCS\_NOTODAY** 스타일 사용\).  
  
-   월 또는 연도에서 팝업 메뉴를 선택 합니다.  
  
 월을 사용자 지정할 수 있습니다 만들 때 개체에 다양 한 스타일을 적용 하 여 달력 컨트롤입니다.  이러한 스타일에 나와  [달 달력 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760919) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Month calendar 컨트롤은 한 달 이상 표시 하 고 굵은 여 특별 휴무일 \(휴일 등\)를 나타낼 수 있습니다 날짜입니다.  
  
 Month calendar 컨트롤 사용에 대 한 자세한 내용은  [를 사용 하 여 CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## 요구 사항  
 **헤더:**  afxdtctl.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl Class](../../mfc/reference/cdatetimectrl-class.md)