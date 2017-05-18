---
title: "CMonthCalCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
dev_langs:
- C++
helpviewer_keywords:
- month calendar controls, CMonthCalCtrl class
- common controls, Internet Explorer 4.0
- CMonthCalCtrl class
- Internet Explorer 4.0 common controls
- month calendar controls
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 96cefbeb7692a07088f596fe08fec2bf179b98bc
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl 클래스
달력 컨트롤의 기능을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|`CMonthCalCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMonthCalCtrl::Create](#create)|Monthcalendar 컨트롤을 만들고 연결 하는 `CMonthCalCtrl` 개체입니다.|  
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|현재 달력 컨트롤의 테두리의 너비를 검색합니다.|  
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|현재 달력 컨트롤에 표시 되는 일정의 수를 검색 합니다.|  
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|현재 달력 컨트롤에 대 한 정보를 검색합니다.|  
|[CMonthCalCtrl::GetCalID](#getcalid)|현재 달력 컨트롤에 대 한 일정 식별자를 검색합니다.|  
|[CMonthCalCtrl::GetColor](#getcolor)|Monthcalendar 컨트롤의 지정된 된 영역 색을 가져옵니다.|  
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|현재 달력 컨트롤에 현재 표시 되는 뷰를 검색 합니다.|  
|[CMonthCalCtrl::GetCurSel](#getcursel)|현재 선택 된 날짜에 표시 된 대로 시스템 시간을 검색 합니다.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|달력의 맨 왼쪽 열에 표시 될 첫 번째 요일을 가져옵니다.|  
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Monthcalendar 컨트롤에서 선택할 수 있는 일 현재 최대 수를 검색 합니다.|  
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|현재 달력 컨트롤에 대 한 "지금" 문자열의 최대 너비를 검색합니다.|  
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Monthcalendar 컨트롤에서 전체 월을 표시 하는 데 필요한 최소 크기를 검색 합니다.|  
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Monthcalendar 컨트롤에 대 한 스크롤 비율을 검색합니다.|  
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|검색 날짜 monthcalendar 컨트롤의 디스플레이의 고가 및 저가 제한을 나타내는 정보입니다.|  
|[CMonthCalCtrl::GetRange](#getrange)|Monthcalendar 컨트롤에서 설정 현재 최소 및 최대 날짜를 검색 합니다.|  
|[CMonthCalCtrl::GetSelRange](#getselrange)|현재 사용자가 선택한 날짜 범위의 상한 및 하 한 제한을 나타내는 날짜 정보를 검색 합니다.|  
|[CMonthCalCtrl::GetToday](#gettoday)|Monthcalendar 컨트롤에 대 한 "현재"로 지정 된 날짜의 날짜 정보를 검색 합니다.|  
|[CMonthCalCtrl::HitTest](#hittest)|화면에 지정된 된 지점에서 달력 컨트롤의 어느 부분 인지 확인 합니다.|  
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|현재 달력 컨트롤의 현재 보기 세기 보기 여부를 나타냅니다.|  
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|현재 달력 컨트롤의 현재 보기&10; 년 보기 여부를 나타냅니다.|  
|[CMonthCalCtrl::IsMonthView](#ismonthview)|현재 달력 컨트롤의 현재 보기 월 보기 여부를 나타냅니다.|  
|[CMonthCalCtrl::IsYearView](#isyearview)|현재 달력 컨트롤의 현재 보기 연도 보기 여부를 나타냅니다.|  
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|현재 달력 컨트롤의 테두리의 너비를 설정합니다.|  
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|현재 달력 컨트롤의 테두리의 기본 너비를 설정합니다.|  
|[CMonthCalCtrl::SetCalID](#setcalid)|현재 달력 컨트롤에 대 한 일정 식별자를 설정합니다.|  
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|세기 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.|  
|[CMonthCalCtrl::SetColor](#setcolor)|Monthcalendar 컨트롤의 지정된 된 영역의 색을 설정 합니다.|  
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|지정된 된 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.|  
|[CMonthCalCtrl::SetCurSel](#setcursel)|Monthcalendar 컨트롤에 대 한 현재 선택 된 날짜를 설정합니다.|  
|[CMonthCalCtrl::SetDayState](#setdaystate)|Monthcalendar 컨트롤의 일에 대 한 표시를 설정합니다.|  
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|현재 월 달력 컨트롤&10; 년 동안 보기를 설정 합니다.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|달력의 맨 왼쪽 열에 표시 되는 요일을 설정 합니다.|  
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|Monthcalendar 컨트롤에서 선택할 수 있는 일의 최대 수를 설정 합니다.|  
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Monthcalendar 컨트롤에 대 한 스크롤 비율을 설정합니다.|  
|[CMonthCalCtrl::SetMonthView](#setmonthview)|월 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.|  
|[CMonthCalCtrl::SetRange](#setrange)|최소 및 최대 허용 monthcalendar 컨트롤에 대 한 날짜를 설정 합니다.|  
|[CMonthCalCtrl::SetSelRange](#setselrange)|월 달력에 대 한 선택을 컨트롤 지정된 된 날짜 범위를 설정 합니다.|  
|[CMonthCalCtrl::SetToday](#settoday)|현재 날짜에 대 한 달력 컨트롤을 설정합니다.|  
|[CMonthCalCtrl::SetYearView](#setyearview)|현재 월 달력 컨트롤 연도 보기를 설정 합니다.|  
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|변경과 월 달력 최소,&1; 개월 크기를 제어 합니다.|  
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|현재 month calendar 컨트롤에 대 한 지정된 된 사각형에 맞는 모든 달력을 포함할 수 있는 가장 작은 사각형을 계산 합니다.|  
  
## <a name="remarks"></a>주의  
 Monthcalendar 컨트롤에서 사용자는 날짜를 선택할 수 있는 간단한 달력 인터페이스를 사용 하 여 사용자를 제공 합니다. 사용자를 표시 하 여 변경할 수 있습니다.:  
  
-   월을 달에서 뒤로 및 앞으로 스크롤입니다.  
  
-   오늘 표시할 텍스트를 현재 날짜를 클릭 하면 (하는 경우는 **MCS_NOTODAY** 스타일 사용 되지 않습니다).  
  
-   월 또는 년 팝업 메뉴에서 선택 합니다.  
  
 월을 사용자 지정할 수 있습니다 컨트롤을 만들 때 다양 한 스타일 개체에 적용 하 여 달력입니다. 이러한 스타일에 설명 된 [Month Calendar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760919) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 Monthcalendar 컨트롤에서&1; 개월 이상를 표시 하 고 (예: 공휴일) 특별 한 날 굵은 글꼴 사용 여부를 나타낼 수 있습니다 날짜입니다.  
  
 Month calendar 컨트롤 사용에 대 한 자세한 내용은 참조 하십시오. [CMonthCalCtrl 사용 하 여](../../mfc/using-cmonthcalctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 있는 afxdtctl.h  
  
##  <a name="cmonthcalctrl"></a>CMonthCalCtrl::CMonthCalCtrl  
 `CMonthCalCtrl` 개체를 생성합니다.  
  
```  
CMonthCalCtrl();
```  
  
### <a name="remarks"></a>주의  
 호출 해야 **만들기** 후 개체를 생성 합니다.  
  
##  <a name="create"></a>CMonthCalCtrl::Create  
 Monthcalendar 컨트롤을 만들고 연결 하는 `CMonthCalCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);

 
virtual BOOL Create(
    DWORD dwStyle,  
    const POINT& pt,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 Month calendar 컨트롤에 적용 된 Windows 스타일의 조합을 지정 합니다. 참조 [Month Calendar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760919) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 스타일에 대 한 자세한 내용은 합니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다. Month calendar 컨트롤의 크기와 위치를 포함합니다.  
  
 `pt`  
 에 대 한 참조는 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) month calendar 컨트롤의 위치를 식별 하는 구조입니다.  
  
 `pParentWnd`  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체 month calendar 컨트롤의 부모 창입니다. 않아야 **NULL**합니다.  
  
 `nID`  
 Month calendar 컨트롤의 컨트롤 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 한 달에 만들 달력의 두 단계에서 제어 합니다.  
  
1.  호출 [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) 생성 하는 `CMonthCalCtrl` 개체입니다.  
  
2.  달력 컨트롤을 만들고에 연결 하는이 멤버 함수를 호출 하 여 `CMonthCalCtrl` 개체입니다.  
  
 호출 하는 경우 **만들기**, 공용 컨트롤 초기화 됩니다. 버전의 **만들기** 있습니다 호출의 크기는 방법을 결정 합니다.  
  
-   한 달에는 컨트롤의 크기를 자동으로 조정 하는 MFC가 호출을 사용 하는 재정의 `pt` 매개 변수입니다.  
  
-   사용자가 직접 컨트롤의 크기를 사용 하 여이 함수의 재정의 호출는 `rect` 매개 변수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&1;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]  
  
##  <a name="getcalendarborder"></a>CMonthCalCtrl::GetCalendarBorder  
 현재 달력 컨트롤의 테두리의 너비를 검색합니다.  
  
```  
int GetCalendarBorder() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 컨트롤 테두리의 너비입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760945) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getcalendarcount"></a>CMonthCalCtrl::GetCalendarCount  
 현재 달력 컨트롤에 표시 되는 일정의 수를 검색 합니다.  
  
```  
int GetCalendarCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Month calendar 컨트롤에 현재 표시 된 달력의 수입니다. 일정의 최대 허용된 개수는 12입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCALENDARCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760947) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getcalendargridinfo"></a>CMonthCalCtrl::GetCalendarGridInfo  
 현재 달력 컨트롤에 대 한 정보를 검색합니다.  
  
```  
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `pmcGridInfo`|에 대 한 포인터는 [MCGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760925) 현재 달력 컨트롤에 대 한 정보를 수신 하는 구조입니다. 호출자가 할당 하 고이 구조를 초기화 하는 일을 담당 합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCALENDARGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760949) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`, 즉 month calendar 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 `GetCalendarGridInfo` 현재 달력 컨트롤에서 표시 되는 달력 날짜를 검색 하는 메서드입니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&3;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]  
  
##  <a name="getcalid"></a>CMonthCalCtrl::GetCalID  
 현재 달력 컨트롤에 대 한 일정 식별자를 검색합니다.  
  
```  
CALID GetCalID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 중 하나는 [일정 식별자](http://msdn.microsoft.com/library/windows/desktop/dd317732) 상수입니다.  
  
### <a name="remarks"></a>주의  
 일정 식별자를 나타내는 지역별 달력을 회교식 양력 (지역화) 또는 일본어와 같은 달력입니다. 응용 프로그램 기능을 지 원하는 다양 한 언어를 가진 일정 식별자를 사용할 수 있습니다.  
  
 이 메서드는 전송 된 [MCM_GETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760951) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getcolor"></a>CMonthCalCtrl::GetColor  
 해당 월의 영역 색 달력에서 지정 된 컨트롤 검색 `nRegion`합니다.  
  
```  
COLORREF GetColor(int nRegion) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nRegion`  
 Monthcalendar 컨트롤에서 색이 검색의 지역입니다. 값의 목록에 대 한 참조는 `nRegion` 의 매개 변수 [SetColor](#setcolor)합니다.  
  
### <a name="return-value"></a>반환 값  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 성공 하는 경우 month calendar 컨트롤의 부분으로 연결 된 색을 지정 하는 값입니다. 그렇지 않은 경우이 멤버 함수는-1을 반환 합니다.  
  
##  <a name="getcurrentview"></a>CMonthCalCtrl::GetCurrentView  
 현재 달력 컨트롤에 현재 표시 되는 뷰를 검색 합니다.  
  
```  
DWORD GetCurrentView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 보기를 다음 값 중 하나에 의해 표시 됩니다.  
  
|값|의미|  
|-----------|-------------|  
|`MCMV_MONTH`|월별 보기|  
|`MCMV_YEAR`|연간 보기|  
|`MCMV_DECADE`|10 년 보기|  
|`MCMV_CENTURY`|세기 보기|  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`, 즉 month calendar 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>예제  
 월 달력을 확인 하는 다음 코드 예제 보고서 컨트롤이 현재 표시 합니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&7;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]  
  
##  <a name="getcursel"></a>CMonthCalCtrl::GetCurSel  
 현재 선택 된 날짜에 표시 된 대로 시스템 시간을 검색 합니다.  
  
```  
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;  
   
BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `refDateTime`  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다. 현재 시간을 받습니다.  
  
 `pDateTime`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조체를 현재 선택 된 날짜 정보를 받게 됩니다. 이 매개 변수는 유효한 주소 여야 하며 수 없습니다 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 otherwize 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb760957)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
> [!NOTE]
>  이 멤버 함수가 실패 하는 경우 스타일 **MCS_MULTISELECT** 설정 됩니다.  
  
 MFC의 구현에서 `GetCurSel`를 지정할 수 있습니다는 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
##  <a name="getfirstdayofweek"></a>CMonthCalCtrl::GetFirstDayOfWeek  
 달력의 맨 왼쪽 열에 표시 될 첫 번째 요일을 가져옵니다.  
  
```  
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pbLocal*  
 에 대 한 포인터는 **BOOL** 값입니다. 값&0;이 아닌 경우 컨트롤의 설정은 제어판에서 설정이 일치 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요일을 나타내는 정수 값입니다. 참조 **주의** 이러한 정수 나타내는 항목에 대 한 자세한 내용은 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb760958)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 요일을 일 다음과 같이 정수로 표현 됩니다.  
  
|값|요일|  
|-----------|---------------------|  
|0|월요일|  
|1|화요일|  
|2|수요일|  
|3|목요일|  
|4|금요일|  
|5|토요일|  
|6|일요일|  
  
### <a name="example"></a>예제  
  예를 참조 [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)합니다.  
  
##  <a name="getmaxselcount"></a>CMonthCalCtrl::GetMaxSelCount  
 Monthcalendar 컨트롤에서 선택할 수 있는 일 현재 최대 수를 검색 합니다.  
  
```  
int GetMaxSelCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤에 대해 선택할 수 있는 일의 총 수를 나타내는 정수 값입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760960)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 이 멤버 함수를 사용 하 여 사용 하 여 컨트롤에 대 한는 **MCS_MULTISELECT** 스타일을 설정 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)합니다.  
  
##  <a name="getmaxtodaywidth"></a>CMonthCalCtrl::GetMaxTodayWidth  
 현재 달력 컨트롤에 대 한 "지금" 문자열의 최대 너비를 검색합니다.  
  
```  
DWORD GetMaxTodayWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 "현재" 문자열 픽셀의 너비입니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`, 즉 month calendar 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제는 `GetMaxTodayWidth` 메서드.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]  
  
### <a name="remarks"></a>주의  
 사용자는 "현재" 문자열을 month calendar 컨트롤의 아래쪽에 표시 되는 클릭 하 여 현재 날짜를 반환할 수 있습니다. 레이블 텍스트 및 날짜 텍스트는 "현재" 문자열에 포함 되어 있습니다.  
  
 이 메서드는 전송 된 [MCM_GETMAXTODAYWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760962) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getminreqrect"></a>CMonthCalCtrl::GetMinReqRect  
 Monthcalendar 컨트롤에서 전체 월을 표시 하는 데 필요한 최소 크기를 검색 합니다.  
  
```  
BOOL GetMinReqRect(RECT* pRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pRect`  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조는 경계 사각형 정보가 표시 됩니다. 이 매개 변수는 유효한 주소 여야 하며 수 없습니다 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면이 멤버 함수 반환&0;이 아닌 및 `lpRect` 해당 경계 정보를 받습니다. 실패할 경우 멤버 함수는 0을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMINREQRECT](http://msdn.microsoft.com/library/windows/desktop/bb760978)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getmonthdelta"></a>CMonthCalCtrl::GetMonthDelta  
 Monthcalendar 컨트롤에 대 한 스크롤 비율을 검색합니다.  
  
```  
int GetMonthDelta() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Month calendar 컨트롤에 대 한 스크롤 비율을 지정 합니다. 스크롤 속도가 스크롤 단추를 두 번 클릭 하는 경우 컨트롤의 디스플레이 이동 하는 개월 수입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb760980)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getmonthrange"></a>CMonthCalCtrl::GetMonthRange  
 검색 날짜 monthcalendar 컨트롤의 디스플레이의 고가 및 저가 제한을 나타내는 정보입니다.  
  
```  
int GetMonthRange(
    COleDateTime& refMinRange,  
    COleDateTime& refMaxRange,  
    DWORD dwFlags) const;  
  
int GetMonthRange(
    CTime& refMinRange,  
    CTime& refMaxRange,  
    DWORD dwFlags) const;  
  
int GetMonthRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange,  
    DWORD dwFlags) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `refMinRange`  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 허용 되는 최소 날짜를 포함 하는 개체입니다.  
  
 `refMaxRange`  
 에 대 한 참조는 `COleDateTime` 또는 `CTime` 허용 되는 최대 날짜를 포함 하는 개체입니다.  
  
 `pMinRange`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.  
  
 `pMaxRange`  
 에 대 한 포인터는 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.  
  
 `dwFlags`  
 검색할 범위 제한의 범위를 지정 하는 값입니다. 이 값에는 다음 중 하나 여야 합니다.  
  
|값|의미|  
|-----------|-------------|  
|GMR_DAYSTATE|앞에 오거나 뒤에 표시 되는 범위 부분적 으로만 표시 되는 월을 포함 합니다.|  
|GMR_VISIBLE|완전히 표시 되는 해당 월만 포함 됩니다.|  
  
### <a name="return-value"></a>반환 값  
 로 표시 된 두 가지 한도 의해 확장 되을 월 단위로 범위를 나타내는 정수입니다 `refMinRange` 및 `refMaxRange` 첫 번째와 두 번째 버전에서는 또는 `pMinRange` 및 `pMaxRange` 세 번째 버전에 있습니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMONTHRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760981)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 `GetMonthRange`를 지정할 수 있습니다 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMonthCalCtrl::SetDayState](#setdaystate)합니다.  
  
##  <a name="getrange"></a>CMonthCalCtrl::GetRange  
 Monthcalendar 컨트롤에서 설정 현재 최소 및 최대 날짜를 검색 합니다.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
  
DWORD GetRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pMinRange`  
 에 대 한 포인터는 `COleDateTime` 개체는 `CTime` 개체 또는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.  
  
 `pMaxRange`  
 에 대 한 포인터는 `COleDateTime` 개체는 `CTime` 개체 또는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 A `DWORD`&0; 일 수 있습니다 (제한이 설정 되어 있음) 또는 제한 정보를 지정 하는 다음 값의 조합입니다.  
  
|값|의미|  
|-----------|-------------|  
|GDTR_MAX|컨트롤에 대 한 최대 한도 설정 됩니다. `pMaxRange` 유효 하 고 해당 날짜 정보를 포함 합니다.|  
|GDTR_MIN|컨트롤에 대 한 최소 제한이 설정 되어 `pMinRange` 유효 하 고 해당 날짜 정보를 포함 합니다.|  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760983)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 `GetRange`를 지정할 수 있습니다는 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&2;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]  
  
##  <a name="getselrange"></a>CMonthCalCtrl::GetSelRange  
 현재 사용자가 선택한 날짜 범위의 상한 및 하 한 제한을 나타내는 날짜 정보를 검색 합니다.  
  
```  
BOOL GetSelRange(
    COleDateTime& refMinRange,  
    COleDateTime& refMaxRange) const;  
  
BOOL GetSelRange(
    CTime& refMinRange,  
    CTime& refMaxRange) const;  
  
BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `refMinRange`  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 허용 되는 최소 날짜를 포함 하는 개체입니다.  
  
 `refMaxRange`  
 에 대 한 참조는 `COleDateTime` 또는 `CTime` 허용 되는 최대 날짜를 포함 하는 개체입니다.  
  
 `pMinRange`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.  
  
 `pMaxRange`  
 에 대 한 포인터는 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760985)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. `GetSelRange`사용 하지 않는 달력 컨트롤에 적용 하는 경우 실패 합니다는 **MCS_MULTISELECT** 스타일입니다.  
  
 MFC의 구현에서 `GetSelRange`를 지정할 수 있습니다 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
##  <a name="gettoday"></a>CMonthCalCtrl::GetToday  
 Monthcalendar 컨트롤에 대 한 "현재"로 지정 된 날짜의 날짜 정보를 검색 합니다.  
  
```  
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;  
   
BOOL GetToday(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `refDateTime`  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 은 현재 날짜를 나타내는 개체입니다.  
  
 `pDateTime`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조를 날짜 정보를 받게 됩니다. 이 매개 변수는 유효한 주소 여야 하며 수 없습니다 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb760987)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 `GetToday`를 지정할 수 있습니다는 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&3;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]  
  
##  <a name="hittest"></a>CMonthCalCtrl::HitTest  
 지정된 된 위치에 있는 경우 어떤 month calendar 컨트롤을 결정 합니다.  
  
```  
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```  
  
### <a name="parameters"></a>매개 변수  
 *pMCHitTest*  
 에 대 한 포인터는 [MCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760927) month calendar 컨트롤에 대 한 적중 테스트를 포함 하는 구조를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 `DWORD` 값입니다. 같은 **uHit** 의 멤버는 **MCHITTESTINFO** 구조입니다.  
  
### <a name="remarks"></a>주의  
 `HitTest`사용 하는 **MCHITTESTINFO** 적중된 테스트에 대 한 정보가 포함 된 구조입니다.  
  
##  <a name="iscenturyview"></a>CMonthCalCtrl::IsCenturyView  
 현재 달력 컨트롤의 현재 보기 세기 보기 여부를 나타냅니다.  
  
```  
BOOL IsCenturyView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `true`현재 보기는 세기 보기; 하는 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 반환 메시지를 `MCMV_CENTURY`,이 메서드는 반환 `true`합니다.  
  
##  <a name="isdecadeview"></a>CMonthCalCtrl::IsDecadeView  
 현재 달력 컨트롤의 현재 보기&10; 년 보기 여부를 나타냅니다.  
  
```  
BOOL IsDecadeView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `true`현재 보기는&10; 년 보기; 하는 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 반환 메시지를 `MCMV_DECADE`,이 메서드는 반환 `true`합니다.  
  
##  <a name="ismonthview"></a>CMonthCalCtrl::IsMonthView  
 현재 달력 컨트롤의 현재 보기 월 보기 여부를 나타냅니다.  
  
```  
BOOL IsMonthView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `true`현재 월 보기; 된 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 반환 메시지를 `MCMV_MONTH`,이 메서드는 반환 `true`합니다.  
  
##  <a name="isyearview"></a>CMonthCalCtrl::IsYearView  
 현재 달력 컨트롤의 현재 보기 연도 보기 여부를 나타냅니다.  
  
```  
BOOL IsYearView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `true`현재 연도 보기; 된 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 반환 메시지를 `MCMV_YEAR`,이 메서드는 반환 `true`합니다.  
  
##  <a name="setcalendarborder"></a>CMonthCalCtrl::SetCalendarBorder  
 현재 달력 컨트롤의 테두리의 너비를 설정합니다.  
  
```  
void SetCalendarBorder(int cxyBorder);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `cxyBorder`|픽셀 단위로 테두리의 너비입니다.|  
  
### <a name="remarks"></a>주의  
 테두리 너비를 설정 성공 하면이 메서드는 `cxyBorder` 매개 변수입니다. 테두리 두께 현재 지정 된 기본 값으로 다시 설정 하는 그렇지 않은 경우 [테마](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), 테마 사용 되지 않는 경우&0;입니다.  
  
 이 메서드는 전송 된 [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`, 즉 month calendar 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>예제  
 드롭다운 달력의 테두리 너비를&8; 픽셀 제어는 다음 코드 예제에서는 설정입니다. 사용 하 여는 [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) 이 메서드가 성공 했는지 여부를 결정할 수 있습니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&6;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]  
  
##  <a name="setcalendarborderdefault"></a>CMonthCalCtrl::SetCalendarBorderDefault  
 현재 달력 컨트롤의 테두리의 기본 너비를 설정합니다.  
  
```  
void SetCalendarBorderDefault();
```  
  
### <a name="remarks"></a>주의  
 테두리 두께입니다. 현재 지정 된 기본 값으로 설정 되어 [테마](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), 테마 사용 되지 않는 경우&0;입니다.  
  
 이 메서드는 전송 된 [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setcalid"></a>CMonthCalCtrl::SetCalID  
 현재 달력 컨트롤에 대 한 일정 식별자를 설정합니다.  
  
```  
BOOL SetCalID(CALID calid);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `calid`|중 하나는 [일정 식별자](http://msdn.microsoft.com/library/windows/desktop/dd317732) 상수입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 일정 식별자 지정 지역별 달력을 회교식 양력 (지역화) 또는 일본어와 같은 달력입니다. 사용 하 여는 `SetCalID` 로 지정 된 달력을 표시 하는 메서드는 `calid` 달력을 포함 하는 로캘 사용자의 컴퓨터에 설치 된 경우 매개 변수입니다.  
  
 이 메서드는 전송 된 [MCM_SETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760995) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`, 즉 month calendar 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 일본 천황 력 달력을 표시 하는 달력 컨트롤을 설정 합니다. `SetCalID` 메서드가 해당 달력 컴퓨터에 설치 된 경우에 성공 합니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&4;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]  
  
##  <a name="setcenturyview"></a>CMonthCalCtrl::SetCenturyView  
 세기 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.  
  
```  
BOOL SetCenturyView();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 보기를 설정 하는 메서드 `MCMV_CENTURY`, 세기 보기를 나타냅니다.  
  
##  <a name="setcolor"></a>CMonthCalCtrl::SetColor  
 Monthcalendar 컨트롤의 지정된 된 영역의 색을 설정 합니다.  
  
```  
COLORREF SetColor(
    int nRegion,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>매개 변수  
 `nRegion`  
 어떤 월 달력으로 설정할 색을 지정 하는 정수 값입니다. 이 값은 다음 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|MCSC_BACKGROUND|월 사이 표시 되는 배경색입니다.|  
|MCSC_MONTHBK|달력에 표시할 배경색입니다.|  
|MCSC_TEXT|달력의 텍스트를 표시하는 데 사용할 색입니다.|  
|MCSC_TITLEBK|달력 제목에 표시할 배경색입니다.|  
|MCSC_TITLETEXT|달력 제목의 텍스트를 표시하는 데 사용할 색입니다.|  
|MCSC_TRAILINGTEXT|헤더 및 후행 일 텍스트를 표시 하는 데 사용 되는 색입니다. 머리글과 후행 일은 현재 달력에 표시 되는 이전 및 다음 달의 날짜입니다.|  
  
 `ref`  
 A **COLORREF** month calendar 컨트롤의 지정된 된 부분에 대 한 새 색 설정에 대 한 값입니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 성공 하는 경우 month calendar 컨트롤의 지정된 된 부분에 대 한 이전 색 설정을 나타내는 값입니다. 그렇지 않으면이 메시지는-1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760997)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&4;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]  
  
##  <a name="setcurrentview"></a>CMonthCalCtrl::SetCurrentView  
 지정된 된 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.  
  
```  
BOOL SetCurrentView(DWORD dwNewView);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `dwNewView`|월, 년,&10; 년 또는 세기 보기를 지정 하는 다음 값 중 하나입니다.<br /><br /> MCMV_MONTH: 월별 보기<br /><br /> MCMV_YEAR: 연간 보기<br /><br /> MCMV_DECADE:&10; 년 보기<br /><br /> MCMV_CENTURY: 세기 보기|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [MCM_SETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760998) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setcursel"></a>CMonthCalCtrl::SetCurSel  
 Monthcalendar 컨트롤에 대 한 현재 선택 된 날짜를 설정합니다.  
  
```  
BOOL SetCurSel(const COleDateTime& refDateTime);  
BOOL SetCurSel(const CTime& refDateTime);  
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>매개 변수  
 `refDateTime`  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 현재 선택 된 month calendar 컨트롤을 나타내는 개체입니다.  
  
 `pDateTime`  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 현재 선택 항목으로 설정할 날짜를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb761002)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 `SetCurSel`를 지정할 수 있습니다는 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&5;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]  
  
##  <a name="setdaystate"></a>CMonthCalCtrl::SetDayState  
 Monthcalendar 컨트롤의 일에 대 한 표시를 설정합니다.  
  
```  
BOOL SetDayState(
    int nMonths,  
    LPMONTHDAYSTATE pStates);
```  
  
### <a name="parameters"></a>매개 변수  
 *nMonths*  
 배열에 있는 요소의 수를 나타내는 값입니다 `pStates` 를 가리킵니다.  
  
 `pStates`  
 에 대 한 포인터는 [MONTHDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760915) month calendar 컨트롤의 디스플레이에서 매일을 그립니다 방법을 정의 하는 값의 배열입니다. **MONTHDAYSTATE** 데이터 형식은 각 비트 (1-31)이 하루에 한 달의 상태를 나타내는 비트 필드입니다. 해당 날짜에 조금 있으면 표시 됩니다 굵게; 그렇지 않으면 없는 중점을 둡니다 표시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb761004)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&6;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]  
  
##  <a name="setdecadeview"></a>CMonthCalCtrl::SetDecadeView  
 현재 월 달력 컨트롤&10; 년 동안 보기를 설정 합니다.  
  
```  
BOOL SetDecadeView();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 보기를 설정 하는 메서드 `MCMV_DECADE`,&10; 년 보기를 나타냅니다.  
  
##  <a name="setfirstdayofweek"></a>CMonthCalCtrl::SetFirstDayOfWeek  
 달력의 맨 왼쪽 열에 표시 되는 요일을 설정 합니다.  
  
```  
BOOL SetFirstDayOfWeek(
    int iDay,  
    int* lpnOld = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *iDay*  
 요일을 나타내는 정수 값으로 첫 번째 요일을 설정 됩니다. 이 값에는 날짜 번호 중 하나 여야 합니다. 참조 [GetFirstDayOfWeek](#getfirstdayofweek) 에 대 한 일 수 있습니다.  
  
 *lpnOld*  
 첫 번째 날 이전에 주를 나타내는 정수에 대 한 포인터를 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 주의 첫 번째 이전 날짜의이 아닌 값으로 설정 된 경우&0;이 아닌 **LOCALE_IFIRSTDAYOFWEEK**, 패널 컨트롤 설정에 표시 된 날짜입니다. 그렇지 않은 경우이 함수는 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb761006)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&7;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]  
  
##  <a name="setmaxselcount"></a>CMonthCalCtrl::SetMaxSelCount  
 Monthcalendar 컨트롤에서 선택할 수 있는 일의 최대 수를 설정 합니다.  
  
```  
BOOL SetMaxSelCount(int nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMax`  
 선택 가능한 일의 최대 수를 나타내는 설정 될 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761008)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CMonthCalCtrl #&8;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]  
  
##  <a name="setmonthdelta"></a>CMonthCalCtrl::SetMonthDelta  
 Monthcalendar 컨트롤에 대 한 스크롤 비율을 설정합니다.  
  
```  
int SetMonthDelta(int iDelta);
```  
  
### <a name="parameters"></a>매개 변수  
 *iDelta*  
 컨트롤의 스크롤 비율으로 설정 하도록 개월 수입니다. 이 값이&0; 이면 월 델타 컨트롤에 표시 하는 개월 수는 기본값으로 다시 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 이전 스크롤 속도입니다. 스크롤 비율 이전에 설정 되지 않은 경우 반환 값은 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb761010)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setmonthview"></a>CMonthCalCtrl::SetMonthView  
 월 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.  
  
```  
BOOL SetMonthView();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 보기를 설정 하는 메서드 `MCMV_MONTH`, 월 보기를 나타냅니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`, 즉 month calendar 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 월, 년,&10; 년 및 세기 보기를 표시 하는 달력 컨트롤을 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;&2;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]  
  
##  <a name="setrange"></a>CMonthCalCtrl::SetRange  
 Monthcalendar 컨트롤에 대 한 최소 및 최대 허용 가능한 날짜를 설정합니다.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);

 
BOOL SetRange(
    const LPSYSTEMTIME pMinRange,  
    const LPSYSTEMTIME pMaxRange);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMinRange`  
 에 대 한 포인터는 `COleDateTime` 개체는 `CTime` 개체 또는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.  
  
 `pMaxRange`  
 에 대 한 포인터는 `COleDateTime` 개체는 `CTime` 개체 또는 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761012)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 `SetRange`를 지정할 수 있습니다 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMonthCalCtrl::GetRange](#getrange)합니다.  
  
##  <a name="setselrange"></a>CMonthCalCtrl::SetSelRange  
 월 달력에 대 한 선택을 컨트롤 지정된 된 날짜 범위를 설정 합니다.  
  
```  
BOOL SetSelRange(
    const COleDateTime& pMinRange,  
    const COleDateTime& pMaxRange);

 
BOOL SetSelRange(
    const CTime& pMinRange,  
    const CTime& pMaxRange);

 
BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,  
    const LPSYSTEMTIME pMaxRange);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMinRange`  
 에 대 한 포인터는 `COleDateTime` 개체는 `CTime` 개체 또는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.  
  
 `pMaxRange`  
 에 대 한 포인터는 `COleDateTime` 개체는 `CTime` 개체 또는 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761014)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 `SetSelRange`를 지정할 수 있습니다 `COleDateTime` 사용는 `CTime` 사용, 또는 `SYSTEMTIME` 구조 사용 합니다.  
  
##  <a name="settoday"></a>CMonthCalCtrl::SetToday  
 현재 날짜에 대 한 달력 컨트롤을 설정합니다.  
  
```  
void SetToday(const COleDateTime& refDateTime);  
void SetToday(const CTime* pDateTime);  
  void SetToday(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>매개 변수  
 `refDateTime`  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 현재 날짜를 포함 하는 개체입니다.  
  
 `pDateTime`  
 두 번째 버전에 대 한 포인터는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 현재 날짜 정보를 포함 하는 개체입니다. 세 번째 버전에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 현재 날짜 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb761016)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMonthCalCtrl::GetToday](#gettoday)합니다.  
  
##  <a name="setyearview"></a>CMonthCalCtrl::SetYearView  
 현재 월 달력 컨트롤 연도 보기를 설정 합니다.  
  
```  
BOOL SetYearView();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 보기를 설정 하는 메서드 `MCMV_YEAR`, 연간 보기를 나타냅니다.  
  
##  <a name="sizeminreq"></a>CMonthCalCtrl::SizeMinReq  
 표시 월 달력 컨트롤의 최소 크기는&1; 개월을 표시 합니다.  
  
```  
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bRepaint`  
 컨트롤이 다시 칠 해 지도록 인지를 지정 합니다. 기본적으로 **TRUE**합니다. 경우 **FALSE**, 발생 하지 다시 표시 합니다.  
  
### <a name="return-value"></a>반환 값  
 Month calendar 컨트롤을 최소값;의 크기는 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출 `SizeMinReq` 성공적으로 한 달의 일정에 대 한 전체 month calendar 컨트롤을 표시 합니다.  
  
##  <a name="sizerecttomin"></a>CMonthCalCtrl::SizeRectToMin  
 현재 month calendar 컨트롤에 대 한 지정된 된 사각형에 맞는 모든 달력을 포함할 수 있는 가장 작은 사각형을 계산 합니다.  
  
```  
LPRECT SizeRectToMin(LPRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `lpRect`|에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 원하는 일정 수를 포함 하는 사각형을 정의 하는 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 사각형 보다 작거나 크기가 사각형을 정의 하는 구조에 의해 정의 된 `lpRect` 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 일정으로 지정 된 사각형에 들어갈 수 있는 계산 된 `lpRect` 매개 변수를 일정의 수에 해당 하는 가장 작은 사각형을 반환 합니다. 실제로이 메서드는 원하는 일정 수를 정확 하 게 맞게 지정된 된 사각형을 축소 합니다.  
  
 이 메서드는 전송 된 [MCM_SIZERECTTOMIN](http://msdn.microsoft.com/library/windows/desktop/bb761020) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl 클래스](../../mfc/reference/cdatetimectrl-class.md)

