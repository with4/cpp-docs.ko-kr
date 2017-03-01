---
title: "CDateTimeCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], CDateTimeCtrl class
- date-picking functionality
- CDateTimeCtrl class
- DateTimePicker control [MFC]
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e5407934021abdb64dfb625e3dfb2c1841b7a5f0
ms.lasthandoff: 02/24/2017

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
|[CDateTimeCtrl::Create](#create)|날짜 및 시간 선택 컨트롤을 만들고 연결 하는 `CDateTimeCtrl` 개체입니다.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색합니다.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|현재 날짜 또는 시간을 표시 하는 데 필요한 날짜 및 시간 선택 컨트롤의 이상적인 크기를 반환 합니다.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|월 달력에서 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 검색 합니다.|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|검색 된 `CMonthCalCtrl` 날짜 및 시간 선택 컨트롤을 연관 된 개체입니다.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|날짜 및 시간 선택 컨트롤의 자식 month calendar 컨트롤에서 현재 사용 되는 글꼴을 검색 합니다.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|현재 날짜 및 시간 선택 컨트롤의 스타일을 가져옵니다.|  
|[CDateTimeCtrl::GetRange](#getrange)|날짜 및 시간 선택 컨트롤에 대 한 시스템 시간을 허용 하는 현재 최소 및 최대 검색 합니다.|  
|[CDateTimeCtrl::GetTime](#gettime)|날짜 및 시간 선택 컨트롤에서 현재 선택 된 시간을 검색 하 고 지정 된 배치 `SYSTEMTIME` 구조입니다.|  
|[CDateTimeCtrl::SetFormat](#setformat)|지정 된 형식 문자열에 따라 날짜 및 시간 선택 컨트롤의 표시를 설정합니다.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|월 달력에서 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 설정합니다.|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|날짜 및 시간 선택 컨트롤의 자식 month calendar 컨트롤에서 사용할 글꼴을 설정 합니다.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|현재 날짜 및 시간 선택 컨트롤의 스타일을 설정 합니다.|  
|[CDateTimeCtrl::SetRange](#setrange)|날짜 및 시간 선택 컨트롤에 대 한 최소 및 최대 허용된 시스템 시간을 설정합니다.|  
|[CDateTimeCtrl::SetTime](#settime)|날짜 및 시간 선택 컨트롤에서 시간을 설정 합니다.|  
  
## <a name="remarks"></a>주의  
 (DTP 컨트롤)의 날짜 및 시간 선택 컨트롤을 사용자와 날짜 및 시간 정보를 교환 하는 간단한 인터페이스를 제공 합니다. 이 인터페이스는 필드를 각각 표시 하는 컨트롤에 저장 된 날짜 및 시간 정보 중 일부를 포함 합니다. 지정된 된 필드에 문자열의 내용을 변경 하 여 컨트롤에 저장 된 정보를 변경할 수 있습니다. 사용자가 마우스 또는 키보드 필드를 사용 하 여 이동할 수 있습니다.  
  
 만들 때 다양 한 스타일 개체에 적용 하 여 날짜 및 시간 선택 컨트롤을 사용자 지정할 수 있습니다. 참조 [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 특정 날짜 및 시간 선택 컨트롤에 스타일에 대 한 자세한 내용은 합니다. 서식 스타일을 사용 하 여 DTP 컨트롤의 표시 형식을 설정할 수 있습니다. 이러한 서식 스타일 "형식 스타일" 아래에서 설명 된 [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)] 항목 [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728)합니다.  
  
 날짜 및 시간 선택 컨트롤 또한 사용 하 여 알림 및에서 설명 하는 콜백을 [CDateTimeCtrl 사용 하 여](../../mfc/using-cdatetimectrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 있는 afxdtctl.h  
  
##  <a name="a-namecdatetimectrla--cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 `CDateTimeCtrl` 개체를 생성합니다.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="a-nameclosemonthcala--cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 현재 날짜 및 시간 선택 컨트롤을 닫습니다.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`, 즉 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 날짜 및 시간 선택 컨트롤에 대 한 드롭다운 달력을 닫습니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="a-namecreatea--cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::Create  
 날짜 및 시간 선택 컨트롤을 만들고 연결 하는 `CDateTimeCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 날짜 시간 컨트롤 스타일의 조합을 지정합니다. 참조 [날짜 및 시간 선택 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761728) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 날짜 및 시간 선택 스타일에 대 한 자세한 내용은 합니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조 날짜 및 시간 선택 컨트롤의 크기와 위치를 합니다.  
  
 `pParentWnd`  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체는 날짜 및 시간 선택 컨트롤의 부모 창입니다. 않아야 **NULL**합니다.  
  
 `nID`  
 날짜 및 시간 선택 컨트롤의 컨트롤 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 만들기에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤을 만들려면  
  
1.  호출 [CDateTimeCtrl](#cdatetimectrl) 생성 하는 `CDateTimeCtrl` 개체입니다.  
  
2.  Windows 날짜 및 시간 선택 컨트롤을 만들고에 연결 하는이 멤버 함수를 호출 하 여 `CDateTimeCtrl` 개체입니다.  
  
 호출 하는 경우 **만들기**, 공용 컨트롤 초기화 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="a-namegetdatetimepickerinfoa--cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색합니다.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `pDateTimePickerInfo`|에 대 한 포인터는 [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729) 현재 날짜 및 시간 선택 컨트롤에 대 한 설명을 받는 구조입니다.<br /><br /> 호출자는이 구조를 할당 하는 일을 담당 합니다. 그러나이 메서드는 초기화는 `cbSize` 구조체의 멤버입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`, 즉 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 성공적으로 검색 여부를 나타냅니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="a-namegetmonthcalcolora--cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 월 달력에서 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 검색 합니다.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `iColor`  
 `int` 색 영역 검색할 월 달력을 지정 하는 값입니다. 값의 목록에 대 한 참조는 `iColor` 에 대 한 매개 변수 [SetMonthCalColor](#setmonthcalcolor)합니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 성공 하는 경우 달력 컨트롤의 지정된 된 부분에 대 한 색 설정을 나타내는 값입니다. 실패 한 경우-1이 반환 됩니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&2;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="a-namegetmonthcalctrla--cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl  
 검색 된 `CMonthCalCtrl` 날짜 및 시간 선택 컨트롤을 연관 된 개체입니다.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) 개체 또는 **NULL** 창이 표시 되는 경우 또는 실패 한 경우.  
  
### <a name="remarks"></a>주의  
 날짜 및 시간 선택 컨트롤에서 드롭다운 화살표를 클릭할 때 자식 달력 컨트롤을 만듭니다. 경우는 `CMonthCalCtrl` 소멸 되기, 응용 프로그램을 날짜 시간 선택 컨트롤의 자식 개월 달력을 나타내는 개체를 저장 합니다. 사용할 수 있어야 하므로, 개체가 더 이상 필요 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="a-namegetmonthcalfonta--cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 날짜 및 시간 선택 컨트롤의 month calendar 컨트롤에서 현재 사용 되는 글꼴을 가져옵니다.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CFont](../../mfc/reference/cfont-class.md) 개체 또는 **NULL** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 `CFont` 반환 값은가 가리키는 개체가 임시 개체 이며 다음 유휴 처리 시간 중에 소멸 됩니다.  
  
##  <a name="a-namegetmonthcalstylea--cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 드롭다운 달력 컨트롤의 현재 날짜 및 시간 선택 컨트롤에 연관 된 스타일을 가져옵니다.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 날짜 및 시간 선택 컨트롤 스타일 (또는) 비트 결합 된 드롭 다운 month calendar 컨트롤의 스타일입니다. 자세한 내용은 참조 [Month Calendar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760919)합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetrangea--cdatetimectrlgetrange"></a><a name="getrange"></a>CDateTimeCtrl::GetRange  
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
  
 두 번째 매개 변수는 유효 합니다. 마찬가지로, 경우  
  
 `return value & GDTR_MIN` == 0  
  
 첫 번째 매개 변수는 유효 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 하나만 지정할 수 있습니다 `COleDateTime` 또는 `CTime` 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="a-namegettimea--cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::GetTime  
 날짜 및 시간 선택 컨트롤에서 현재 선택 된 시간을 검색 하 고 지정 된 배치 `SYSTEMTIME` 구조입니다.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *timeDest*  
 첫 번째 버전에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 시스템 시간 정보를 받게 될 개체입니다. 두 번째 버전에 대 한 참조는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 시스템 시간 정보를 받게 될 개체입니다.  
  
 *pTimeDest*  
 에 대 한 포인터는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조 시스템 시간 정보를 얻습니다. 이 아니어야 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 시간에 성공적으로 기록 되는 경우 0이 아니고 첫 번째 버전에는 `COleDateTime` 개체 하 고, 그렇지 않으면 0입니다. 두 번째 및 세 번째 버전에서는 `DWORD` 값과 같은 **dwFlag** 집합의 구성원은 [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) 구조입니다. 참조는 **주의** 에 대 한 자세한 내용은 아래 섹션입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC 구현에서 **GetTime**, 사용할 수 있습니다 `COleDateTime` 또는 `CTime` 클래스에 사용할 수는 `SYSTEMTIME` 구조를 시간 정보를 저장 합니다.  
  
 반환 값은 `DWORD` 두 번째와 세 번째 버전에서는 위, 나타내는 날짜 및 시간 선택 컨트롤 "날짜 없음" 상태로 설정 되어 있는지 여부에 표시 된 대로 [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) 구조체 멤버 `dwFlags`합니다. 값 반환 equals **GDT_NONE**, 컨트롤 "날짜 없음" 상태를로 설정 되 고 사용 하 여는 **DTS_SHOWNONE** 스타일입니다. 값 반환 equals **GDT_VALID**, 시스템 시간은 대상 위치에 성공적으로 저장 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="a-namegetidealsizea--cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 현재 날짜 또는 시간을 표시 하는 데 필요한 날짜 및 시간 선택 컨트롤의 이상적인 크기를 반환 합니다.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `psize`|에 대 한 포인터는 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 컨트롤에 대 한 이상적인 크기를 포함 하는 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 반환 값은 항상 `true`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`, 즉 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 날짜 및 시간 선택 컨트롤을 표시 하는 이상적인 크기를 검색 합니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&2;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="a-namesetformata--cdatetimectrlsetformat"></a><a name="setformat"></a>CDateTimeCtrl::SetFormat  
 지정 된 형식 문자열에 따라 날짜 및 시간 선택 컨트롤의 표시를 설정합니다.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrFormat*  
 원하는 표시를 정의 하는&0;으로 끝나는 형식 문자열에 대 한 포인터입니다. 이 매개 변수를 설정 **NULL** 현재 스타일에 대 한 기본 형식 문자열에 컨트롤을 다시 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
> [!NOTE]
>  사용자 입력이이 호출의 성공 또는 실패를 확인 하지 않습니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&6;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="a-namesetmonthcalcolora--cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 월 달력에서 날짜 및 시간 선택 컨트롤 내에서 특정된 부분에 대 한 색을 설정합니다.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>매개 변수  
 `iColor`  
 `int`영역을 설정 하는 달력 컨트롤을 지정 하는 값입니다. 이 값은 다음 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|MCSC_BACKGROUND|월 사이 표시 되는 배경색을 설정 합니다.|  
|MCSC_MONTHBK|한 달 내에 표시 되는 배경색을 설정 합니다.|  
|MCSC_TEXT|한 달 내 텍스트를 표시 하는 데 사용 하 여 색을 설정 합니다.|  
|MCSC_TITLEBK|달력의 제목에 표시 되는 배경 색을 설정 합니다.|  
|MCSC_TITLETEXT|내 달력의 제목 텍스트를 표시 하는 데 사용 하 여 색을 설정 합니다.|  
|MCSC_TRAILINGTEXT|헤더 및 후행 일 텍스트 표시에 사용 되는 색을 설정 합니다. 머리글과 후행 일은 현재 달력에 표시 되는 이전 및 다음 달의 날짜입니다.|  
  
 `ref`  
 A **COLORREF** 드롭다운 달력의 지정된 된 영역에 대해 설정할 색을 나타내는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 성공 하는 경우 달력 컨트롤의 지정된 된 부분에 대 한 이전 색 설정을 나타내는 값입니다. 그렇지 않으면 메시지는-1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)합니다.  
  
##  <a name="a-namesetmonthcalfonta--cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont  
 날짜 및 시간 선택 컨트롤의 자식 month calendar 컨트롤에서 사용할 글꼴을 설정 합니다.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hFont`  
 설정 될 글꼴에 대 한 핸들입니다.  
  
 `bRedraw`  
 여부 컨트롤은 즉시 다시 그리도록 글꼴 설정 시를 지정 합니다. 이 매개 변수를 설정 **TRUE** 해당 컨트롤이 컨트롤을 다시 그리도록 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&7;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  멤버를 확인 해야이 코드를 사용 하는 경우 프로그램 `CDialog`-라는 클래스를 파생 `m_MonthFont` 형식의 **CFont**합니다.  
  
##  <a name="a-namesetmonthcalstylea--cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 드롭다운 달력 컨트롤 연결 된 현재 날짜 및 시간 선택 컨트롤의 스타일을 설정 합니다.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `dwStyle`|새로운 달 달력 month calendar 컨트롤 스타일의 비트 조합 (OR) 컨트롤 스타일입니다. 자세한 내용은 참조 [Month Calendar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760919)합니다.|  
  
### <a name="return-value"></a>반환 값  
 드롭다운 달력 컨트롤의 이전 스타일입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_dateTimeCtrl`, 즉 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 약식된 이름이 요일, 그리고 오늘 표시기 없음의 일, 주 수를 표시 하려면 날짜 및 시간 선택 컨트롤을 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;&3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="a-namesetrangea--cdatetimectrlsetrange"></a><a name="setrange"></a>CDateTimeCtrl::SetRange  
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
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC의 구현에서 하나만 지정할 수 있습니다 `COleDateTime` 또는 `CTime` 사용 합니다. 하는 경우는 `COleDateTime` 개체에는 **NULL** 상태, 범위 제거 됩니다. 하는 경우는 `CTime` 포인터 또는 `COleDateTime` 포인터가 **NULL**, 범위 제거 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CDateTimeCtrl::GetRange](#getrange)합니다.  
  
##  <a name="a-namesettimea--cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl::SetTime  
 날짜 및 시간 선택 컨트롤에서 시간을 설정 합니다.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *timeNew*  
 에 대 한 참조는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를 포함 하는 컨트롤 설정 해야 합니다.  
  
 *pTimeNew*  
 두 번째 버전에 대 한 포인터 위에 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 컨트롤을 설정할 시간을 포함 하는 개체입니다. 에 대 한 포인터 위의 세 번째 버전에는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 컨트롤을 설정할 시간을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC 구현에서 **SetTime**를 사용할 수 있습니다는 `COleDateTime` 또는 `CTime` 클래스에 사용할 수는 `SYSTEMTIME` 시간 정보를 설정 하려면 구조입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CDateTimeCtrl #&8;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl 클래스](../../mfc/reference/cmonthcalctrl-class.md)

