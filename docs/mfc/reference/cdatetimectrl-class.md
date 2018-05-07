---
title: CDateTimeCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
dev_langs:
- C++
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80b63c6bd44b6d3606b7807913f1e3ae1b4e33f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl 클래스
날짜 및 시간 선택 컨트롤의 기능을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|`CDateTimeCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|현재 날짜 및 시간 선택 컨트롤을 닫습니다.|  
|[CDateTimeCtrl::Create](#create)|날짜 및 시간 선택 컨트롤을 만들고에 연결 된 `CDateTimeCtrl` 개체입니다.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색합니다.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|현재 날짜 또는 시간을 표시 하는 데 필요한 날짜 및 시간 선택 컨트롤의 이상적인 크기를 반환 합니다.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|월 달력 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 검색 합니다.|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|검색 된 `CMonthCalCtrl` 날짜 및 시간 선택 컨트롤을 연관 된 개체입니다.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|현재 날짜와 시간 선택 컨트롤의 자식 monthcalendar 컨트롤에서 사용 되는 글꼴을 검색 합니다.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|현재 날짜 및 시간 선택 컨트롤의 스타일을 가져옵니다.|  
|[CDateTimeCtrl::GetRange](#getrange)|날짜 및 시간 선택 컨트롤에 대 한 시스템 시간을 허용 하는 현재 최소 및 최대 검색 합니다.|  
|[CDateTimeCtrl::GetTime](#gettime)|날짜 및 시간 선택 컨트롤에서 현재 선택 된 시간을 검색 하 고에 지정 된 배치 `SYSTEMTIME` 구조입니다.|  
|[CDateTimeCtrl::SetFormat](#setformat)|지정 된 형식 문자열에 따라 날짜 및 시간 선택 컨트롤의 표시를 설정합니다.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|월 달력 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 설정합니다.|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|날짜 및 시간 선택 컨트롤의 자식 monthcalendar 컨트롤에서 사용할 글꼴을 설정 합니다.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|현재 날짜 및 시간 선택 컨트롤의 스타일을 설정 합니다.|  
|[CDateTimeCtrl::SetRange](#setrange)|날짜 및 시간 선택 컨트롤에 대 한 최소 및 최대 허용된 시스템 시간을 설정합니다.|  
|[CDateTimeCtrl::SetTime](#settime)|날짜 및 시간 선택 컨트롤에서 시간을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 날짜 및 시간 선택 컨트롤 (DTP 컨트롤)는 사용자와 날짜 및 시간 정보를 교환할 간단한 인터페이스를 제공 합니다. 이 인터페이스는 필드를 각각 표시 하는 컨트롤에 저장 된 날짜 및 시간 정보의 일부를 포함 합니다. 지정된 된 필드에 문자열의 내용을 변경 하 여 컨트롤에 저장 된 정보를 변경할 수 있습니다. 마우스 또는 키보드 필드를 사용 하 여 이동할 수 있습니다.  
  
 만들 때 개체에 다양 한 스타일을 적용 하 여 날짜 및 시간 선택 컨트롤을 사용자 지정할 수 있습니다. 참조 [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728) 스타일의 날짜 및 시간 선택 컨트롤에 대 한 자세한 내용은 Windows sdk입니다. 서식 스타일을 사용 하 여 DTP 컨트롤의 표시 형식을 설정할 수 있습니다. Windows SDK 항목에서 이러한 형식 스타일 "서식 스타일" 아래에서 설명 [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728)합니다.  
  
 날짜 및 시간 선택 컨트롤은 또한 알림 및에서 설명 하는 콜백을 사용 [CDateTimeCtrl 사용 하 여](../../mfc/using-cdatetimectrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 있는 afxdtctl.h  
  
##  <a name="cdatetimectrl"></a>  CDateTimeCtrl::CDateTimeCtrl  
 `CDateTimeCtrl` 개체를 생성합니다.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="closemonthcal"></a>  CDateTimeCtrl::CloseMonthCal  
 현재 날짜 및 시간 선택 컨트롤을 닫습니다.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 날짜 및 시간 선택 컨트롤에 대 한 드롭다운 달력을 닫습니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="create"></a>  CDateTimeCtrl::Create  
 날짜 및 시간 선택 컨트롤을 만들고에 연결 된 `CDateTimeCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 날짜 시간 컨트롤 스타일의 조합을 지정합니다. 참조 [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728) 날짜 및 시간 선택 스타일에 대 한 자세한 내용은 Windows sdk입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 날짜 및 시간 선택 컨트롤의 크기와 위치입니다.  
  
 `pParentWnd`  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체 날짜 및 시간 선택 컨트롤의 부모 창입니다. 않아야 **NULL**합니다.  
  
 `nID`  
 지정 된 날짜 및 시간 선택 컨트롤의 컨트롤 id입니다.  
  
### <a name="return-value"></a>반환 값  
 만들기에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤을 만들려면  
  
1.  호출 [CDateTimeCtrl](#cdatetimectrl) 생성 하는 `CDateTimeCtrl` 개체입니다.  
  
2.  Windows 날짜 및 시간 선택 컨트롤을 만들고에 연결 하는이 멤버 함수 호출의 `CDateTimeCtrl` 개체입니다.  
  
 호출 하는 경우 **만들기**, 공용 컨트롤은 초기화 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="getdatetimepickerinfo"></a>  CDateTimeCtrl::GetDateTimePickerInfo  
 현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색합니다.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `pDateTimePickerInfo`|에 대 한 포인터는 [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729) 구조체는 현재 날짜 및 시간 선택 컨트롤의 설명입니다.<br /><br /> 호출자는이 구조를 할당 하는 일을 담당 합니다. 그러나이 메서드는 초기화는 `cbSize` 구조체의 멤버입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 성공적으로 현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색 하는지 여부를 나타냅니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="getmonthcalcolor"></a>  CDateTimeCtrl::GetMonthCalColor  
 월 달력 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 검색 합니다.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `iColor`  
 `int` 검색할 monthcalendar의 색 영역을 지정 하는 값입니다. 값 목록에 대 한 참조는 `iColor` 에 대 한 매개 변수 [SetMonthCalColor](#setmonthcalcolor)합니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 성공 하는 경우 month calendar 컨트롤의 지정된 된 부분에 대 한 색 설정을 나타내는 값입니다. 실패 한 경우-1이 반환 됩니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="getmonthcalctrl"></a>  CDateTimeCtrl::GetMonthCalCtrl  
 검색 된 `CMonthCalCtrl` 날짜 및 시간 선택 컨트롤을 연관 된 개체입니다.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) 개체 또는 **NULL** 는 창이 표시 되지 않은 경우 또는 실패 한 경우.  
  
### <a name="remarks"></a>설명  
 날짜 및 시간 선택 컨트롤에서 드롭다운 화살표를 클릭할 때 자식 month calendar 컨트롤을 만듭니다. 경우는 `CMonthCalCtrl` 소멸 되기, 응용 프로그램을 날짜 시간 선택 컨트롤의 자식 개월 달력을 나타내는 개체를 저장 합니다. 사용할 수 있어야 하므로, 개체가 더 이상 필요 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="getmonthcalfont"></a>  CDateTimeCtrl::GetMonthCalFont  
 현재 날짜와 시간 선택 컨트롤의 monthcalendar 컨트롤에서 사용 되는 글꼴을 가져옵니다.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CFont](../../mfc/reference/cfont-class.md) 개체 또는 **NULL** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 `CFont` 반환 값으로 가리키는 개체가 임시 개체 이며 다음 유휴 처리 시간 동안 제거 됩니다.  
  
##  <a name="getmonthcalstyle"></a>  CDateTimeCtrl::GetMonthCalStyle  
 연결 된 현재 날짜 및 시간 선택 컨트롤 드롭 다운 month calendar 컨트롤의 스타일을 가져옵니다.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 비트 결합 된 드롭 다운 month calendar 컨트롤 (또는) 날짜 및 시간 선택 컨트롤 스타일의 스타일입니다. 자세한 내용은 참조 [Month Calendar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760919)합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getrange"></a>  CDateTimeCtrl::GetRange  
 날짜 및 시간 선택 컨트롤에 대 한 시스템 시간을 허용 하는 현재 최소 및 최대 검색 합니다.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pMinRange`  
 에 대 한 포인터는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 허용 되는 가장 빠른 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.  
  
 `pMaxRange`  
 에 대 한 포인터는 `COleDateTime` 개체 또는 `CTime` 개체에 허용 되는 최신 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 A `DWORD` 범위는 설정 여부를 나타내는 플래그를 포함 하는 값입니다. 조건  
  
 `return value & GDTR_MAX` == 0  
  
 다음 두 번째 매개 변수는 유효 합니다. 마찬가지로, 하는 경우  
  
 `return value & GDTR_MIN` == 0  
  
 그런 다음 첫 번째 매개 변수는 유효 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 하나만 지정할 수 있습니다 `COleDateTime` 또는 `CTime` 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="gettime"></a>  CDateTimeCtrl::GetTime  
 날짜 및 시간 선택 컨트롤에서 현재 선택 된 시간을 검색 하 고에 지정 된 배치 `SYSTEMTIME` 구조입니다.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *timeDest*  
 첫 번째 버전에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 시스템 시간 정보를 받게 될 개체입니다. 두 번째 버전에 대 한 참조는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 시스템 시간 정보를 받게 될 개체입니다.  
  
 *pTimeDest*  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조 시스템 시간 정보를 얻습니다. 않아야 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 시간에 성공적으로 기록 하는 경우 0이 아니고 첫 번째 버전에는 `COleDateTime` 개체가 고, 그렇지 않으면 0입니다. 두 번째 및 세 번째 버전에서는 `DWORD` 값과 같지는 **dwFlag** 집합의 구성원은 [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) 구조입니다. 참조는 **주의** 자세한 내용은 아래 섹션.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769)Windows SDK에 설명 된 대로 합니다. MFC 구현에서 **GetTime**를 사용할 수 있습니다 `COleDateTime` 또는 `CTime` 클래스 또는 있습니다 사용할 수는 `SYSTEMTIME` 구조 시간 정보를 저장 합니다.  
  
 반환 값 `DWORD` 두 번째 및 세 번째 버전에서는 위, 이면 여부 날짜 및 시간 선택 컨트롤은으로 설정 "날짜 없음" 상태에 표시 된 대로 [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) 구조체 멤버 `dwFlags`합니다. 값 반환 equals **GDT_NONE**, 컨트롤이 "날짜 없음" 상태로 설정 되 고 사용 하 여는 **DTS_SHOWNONE** 스타일입니다. 값 반환 equals **GDT_VALID**, 시스템 시간은 대상 위치에 성공적으로 저장 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="getidealsize"></a>  CDateTimeCtrl::GetIdealSize  
 현재 날짜 또는 시간을 표시 하는 데 필요한 날짜 및 시간 선택 컨트롤의 이상적인 크기를 반환 합니다.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `psize`|에 대 한 포인터는 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 컨트롤에 대 한 이상적인 크기를 포함 하는 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 반환 값은 항상 `true`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 날짜 및 시간 선택 컨트롤을 표시 하는 이상적인 크기를 검색 합니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="setformat"></a>  CDateTimeCtrl::SetFormat  
 지정 된 형식 문자열에 따라 날짜 및 시간 선택 컨트롤의 표시를 설정합니다.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrFormat*  
 원하는 표시 오프셋을 정의 하는 0으로 끝나는 서식 문자열에 대 한 포인터입니다. 이 매개 변수를 설정 **NULL** 컨트롤 현재 스타일에 대 한 기본 형식 문자열을 다시 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
> [!NOTE]
>  사용자 입력이이 호출의 성공 또는 실패를 확인 하지 않습니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="setmonthcalcolor"></a>  CDateTimeCtrl::SetMonthCalColor  
 월 달력 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 설정합니다.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>매개 변수  
 `iColor`  
 `int` 영역을 설정 하려면 month calendar 컨트롤을 지정 하는 값입니다. 이 값은 다음 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|MCSC_BACKGROUND|개월 사이 표시 되는 배경색을 설정 합니다.|  
|MCSC_MONTHBK|한 달 내에 표시 되는 배경색을 설정 합니다.|  
|MCSC_TEXT|한 달 내 텍스트를 표시 하는 데 사용할 색을 설정 합니다.|  
|MCSC_TITLEBK|달력의 제목에 표시 되는 배경색을 설정 합니다.|  
|MCSC_TITLETEXT|내 달력의 제목 텍스트를 표시 하는 데 사용할 색을 설정 합니다.|  
|MCSC_TRAILINGTEXT|헤더 및 후행 날짜 텍스트를 표시 하는 데 사용할 색을 설정 합니다. 헤더와 후행 날짜는 현재 달력에 나타나는 이전 및 다음 달의 날짜입니다.|  
  
 `ref`  
 A **COLORREF** 월 달력의 지정된 된 영역에 대해 설정할 색을 나타내는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 성공 하는 경우 month calendar 컨트롤의 지정된 된 부분에 대 한 이전 색 설정을 나타내는 값입니다. 그렇지 않으면 메시지는-1을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)합니다.  
  
##  <a name="setmonthcalfont"></a>  CDateTimeCtrl::SetMonthCalFont  
 날짜 및 시간 선택 컨트롤의 자식 monthcalendar 컨트롤에서 사용할 글꼴을 설정 합니다.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hFont`  
 설정 되는 글꼴에 대 한 핸들입니다.  
  
 `bRedraw`  
 글꼴 설정 시 컨트롤을 즉시 그려집니다 있는지 여부를 지정 합니다. 이 매개 변수를 설정 **TRUE** 해당 컨트롤이 컨트롤을 다시 그리도록 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  멤버로 설정 해야이 코드를 사용 하는 경우 프로그램 `CDialog`-라는 클래스를 파생 `m_MonthFont` 형식의 **CFont**합니다.  
  
##  <a name="setmonthcalstyle"></a>  CDateTimeCtrl::SetMonthCalStyle  
 연결 된 현재 날짜 및 시간 선택 컨트롤 드롭 다운 month calendar 컨트롤의 스타일을 설정 합니다.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `dwStyle`|새로운 달 calendar month calendar 컨트롤 스타일의 비트 조합 (OR) 컨트롤 스타일입니다. 자세한 내용은 참조 [Month Calendar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760919)합니다.|  
  
### <a name="return-value"></a>반환 값  
 드롭다운 달력 컨트롤의 이전 스타일입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 약식된 이름이 요일과 오늘의 표시가 없는 일, 주 수를 표시 하려면 날짜 및 시간 선택 컨트롤을 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="setrange"></a>  CDateTimeCtrl::SetRange  
 날짜 및 시간 선택 컨트롤에 대 한 최소 및 최대 허용된 시스템 시간을 설정합니다.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMinRange`  
 에 대 한 포인터는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 허용 되는 가장 빠른 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.  
  
 `pMaxRange`  
 에 대 한 포인터는 `COleDateTime` 개체 또는 `CTime` 개체에 허용 되는 최신 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 하나만 지정할 수 있습니다 `COleDateTime` 또는 `CTime` 사용 합니다. 경우는 `COleDateTime` 개체에는 **NULL** 상태 범위 제거 됩니다. 경우는 `CTime` 포인터 또는 `COleDateTime` 포인터가 **NULL**, 범위 제거 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CDateTimeCtrl::GetRange](#getrange)합니다.  
  
##  <a name="settime"></a>  CDateTimeCtrl::SetTime  
 날짜 및 시간 선택 컨트롤에서 시간을 설정합니다.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *timeNew*  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를 포함 하는 컨트롤 설정 됩니다.  
  
 *pTimeNew*  
 두 번째 버전에 대 한 포인터 위에 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 컨트롤을 설정할 시간을 포함 하는 개체입니다. 에 대 한 포인터 위에 세 번째 버전에는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 컨트롤을 설정할 시간을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782)Windows SDK에 설명 된 대로 합니다. MFC 구현에서 **SetTime**를 사용할 수 있습니다는 `COleDateTime` 또는 `CTime` 클래스 또는 있습니다 사용할 수는 `SYSTEMTIME` 구조 시간 정보를 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl 클래스](../../mfc/reference/cmonthcalctrl-class.md)
