---
title: "CSpinButtonCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSpinButtonCtrl
- CSpinButtonCtrl class
- CSpinButtonCtrl class, common controls
- up-down controls, spin button control
- spin button control
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
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
ms.openlocfilehash: 486a0842ed04f0e760bbb332986a97a35ce9851f
ms.lasthandoff: 02/24/2017

---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl 클래스
Windows의 공용 스핀 단추 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|`CSpinButtonCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|스핀 단추 컨트롤을 만들고에 연결 된 `CSpinButtonCtrl` 개체입니다.|  
|[CSpinButtonCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 스핀 단추 컨트롤을 만들고에 연결 된 `CSpinButtonCtrl` 개체입니다.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|스핀 단추 컨트롤에 대 한 가속 정보를 검색합니다.|  
|[CSpinButtonCtrl::GetBase](#getbase)|스핀 단추 컨트롤에 대 한 현재 자료를 검색합니다.|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|현재 버디 창에 대 한 포인터를 검색합니다.|  
|[CSpinButtonCtrl::GetPos](#getpos)|스핀 단추 컨트롤의 현재 위치를 검색합니다.|  
|[CSpinButtonCtrl::GetRange](#getrange)|스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 검색합니다.|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|스핀 단추 컨트롤에 대 한 가속을 설정합니다.|  
|[CSpinButtonCtrl::SetBase](#setbase)|스핀 단추 컨트롤에 대 한 기본을 설정입니다.|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|스핀 단추 컨트롤에 대 한 버디 창을 설정입니다.|  
|[CSpinButtonCtrl::SetPos](#setpos)|컨트롤에 대 한 현재 위치를 설정합니다.|  
|[CSpinButtonCtrl::SetRange](#setrange)|스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 "스핀 단추 컨트롤" (up-down 컨트롤이 라고도 함)는 사용자를 증가 또는 감소 같은 스크롤 위치 또는 관련 컨트롤에 표시 된 숫자 값을 클릭할 수 있는 화살표 단추 쌍입니다. 스핀 단추 컨트롤에 연관 된 값의 현재 위치를 라고 합니다. 스핀 단추 컨트롤은 "버디 창입니다." 이라는 도우미 컨트롤을 가장 많이 사용  
  
 이 컨트롤 (및 따라서는 `CSpinButtonCtrl` 클래스)은 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.  
  
 사용자에 게 스핀 단추 컨트롤 및 버디 창 처럼 표시 됩니다 단일 컨트롤입니다. 스핀 단추 컨트롤이 자동으로 자체의 버디 창 옆에 있는 놓고 자동으로 설정 있는지 버디 창의 캡션을 현재 위치를 지정할 수 있습니다. 편집 컨트롤이 포함 된 숫자 입력을 위해 사용자에 게 묻는 스핀 단추 컨트롤을 사용할 수 있습니다.  
  
 최대값으로 현재 위치를 이동 위쪽 화살표를 클릭 하면 하 고 최소한으로 현재 위치를 이동 아래쪽 화살표를 클릭 합니다. 기본적으로 최소값은 100 이며, 최대값은 0입니다. 최소 설정 (예를 들어 경우 기본 설정이 사용 됩니다) 설정, 위쪽 화살표 감소를 클릭 하는 최대값 보다 크면 언제 든 지 위치 값 및 아래쪽 화살표를 클릭 하면 늘립니다.  
  
 스핀 단추 컨트롤 버디 창 없이 간소화 된 스크롤 막대의 일종으로 작동합니다. 예를 들어 탭 컨트롤은 때때로 추가 탭 보기로 스크롤할 수 있도록 스핀 단추 컨트롤을 표시 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CSpinButtonCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CSpinButtonCtrl 사용 하 여](../../mfc/using-cspinbuttonctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="create"></a>CSpinButtonCtrl::Create  
 스핀 단추 컨트롤을 만들고에 연결 된 `CSpinButtonCtrl` 개체...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 스핀 단추 컨트롤의 스타일을 지정합니다. 스핀 단추 컨트롤 스타일의 조합이 컨트롤에 적용 됩니다. 이러한 스타일에 설명 된 [Up-down 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759885) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 스핀 단추 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조  
  
 `pParentWnd`  
 스핀 단추 컨트롤의 부모 창, 일반적으로에 대 한 포인터는 `CDialog`합니다. 않아야 **NULL입니다.**  
  
 `nID`  
 스핀 단추 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CSpinButtonCtrl` 처음 두 단계에서 개체의 생성자를 호출 하 고, 호출 하 **만들기**, 스핀 단추 컨트롤을 만들고 연결에는 `CSpinButtonCtrl` 개체입니다.  
  
 스핀 단추 컨트롤이 확장된 창 스타일을 만들려면 호출 [CSpinButtonCtrl::CreateEx](#createex) 대신 **만들기**합니다.  
  
##  <a name="createex"></a>CSpinButtonCtrl::CreateEx  
 컨트롤 (자식 창)와 연결 된 `CSpinButtonCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 생성 되는 컨트롤의 확장된 스타일을 지정 합니다. 확장된 창 스타일의 목록에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 스핀 단추 컨트롤의 스타일을 지정합니다. 스핀 단추 컨트롤 스타일의 조합이 컨트롤에 적용 됩니다. 이러한 스타일에 설명 된 [Up-down 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759885) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에서 만든 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 앞에 지정 된 Windows 확장된 스타일을 적용 하려면 **WS_EX_**합니다.  
  
##  <a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl  
 `CSpinButtonCtrl` 개체를 생성합니다.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>CSpinButtonCtrl::GetAccel  
 스핀 단추 컨트롤에 대 한 가속 정보를 검색합니다.  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nAccel`  
 지정 된 배열에 있는 요소의 수 `pAccel`합니다.  
  
 `pAccel`  
 배열에 대 한 포인터 [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) 가속 정보를 수신 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 엑셀 러 레이 터 구조 수 검색 합니다.  
  
##  <a name="getbase"></a>CSpinButtonCtrl::GetBase  
 스핀 단추 컨트롤에 대 한 현재 자료를 검색합니다.  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 기준 값입니다.  
  
##  <a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy  
 현재 버디 창에 대 한 포인터를 검색합니다.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 버디 창에 대 한 포인터입니다.  
  
##  <a name="getpos"></a>CSpinButtonCtrl::GetPos  
 스핀 단추 컨트롤의 현재 위치를 검색합니다.  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  ```  
  
### Parameters  
 *lpbError*  
 A pointer to a boolean value that is set to zero if the value is successfully retrieved or non-zero if an error occurs. If this parameter is set to **NULL**, errors are not reported.  
  
### Return Value  
 The first version returns the 16-bit current position in the low-order word. The high-order word is nonzero if an error occurred.  
  
 The second version returns the 32-bit position.  
  
### Remarks  
 When it processes the value returned, the control updates its current position based on the caption of the buddy window. The control returns an error if there is no buddy window or if the caption specifies an invalid or out-of-range value.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 Retrieves the upper and lower limits (range) for a spin button control.  
  
```  
DWORD GetRange() const;  
  
void GetRange (int / 낮은  
    int 위쪽 / /) const;  
  
GetRange32 void (int 낮은, / /  
    int 위쪽 / /) const;  
```  
  
### Parameters  
 *lower*  
 Reference to an integer that receives the lower limit for the control.  
  
 *upper*  
 Reference to an integer that receives the upper limit for the control.  
  
### Return Value  
 The first version returns a 32-bit value containing the upper and lower limits. The low-order word is the upper limit for the control, and the high-order word is the lower limit.  
  
### Remarks  
 The member function `GetRange32` retrieves the spin button control's range as a 32-bit integer.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 Sets the acceleration for a spin button control.  
  
```  
BOOL SetAccel (int nAccel,  
    UDACCEL* pAccel);
```  
  
### Parameters  
 `nAccel`  
 Number of [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) structures specified by `pAccel`.  
  
 `pAccel`  
 Pointer to an array of `UDACCEL` structures, which contain acceleration information. Elements should be sorted in ascending order based on the **nSec** member.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 Sets the base for a spin button control.  
  
```  
int SetBase (int nBase);
```  
  
### Parameters  
 `nBase`  
 New base value for the control. It can be 10 for decimal or 16 for hexadecimal.  
  
### Return Value  
 The previous base value if successful, or zero if an invalid base is given.  
  
### Remarks  
 The base value determines whether the buddy window displays numbers in decimal or hexadecimal digits. Hexadecimal numbers are always unsigned; decimal numbers are signed.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 Sets the buddy window for a spin button control.  
  
```  
CWnd* SetBuddy (CWnd* pWndBuddy);
```  
  
### Parameters  
 `pWndBuddy`  
 Pointer to the new buddy window.  
  
### Return Value  
 A pointer to the previous buddy window.  
  
### Remarks  
 A spin control is almost always associated with another window, such as an edit control, that displays some content. This other window is called the "buddy" of the spin control.  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 Sets the current position for a spin button control.  
  
```  
int SetPos (int nPos);  
int SetPos32(int nPos);
```  
  
### Parameters  
 `nPos`  
 New position for the control. This value must be in the range specified by the upper and lower limits for the control.  
  
### Return Value  
 The previous position (16-bit precision for `SetPos`, 32-bit precision for `SetPos32`).  
  
### Remarks  
 `SetPos32` sets the 32-bit position.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange  
 Sets the upper and lower limits (range) for a spin button control.  
  
```  
void SetRange (짧은 nLower,  
    짧은 nUpper);

 
SetRange32 void (int nLower,  
    int nUpper);
```  
  
### Parameters  
 `nLower`and `nUpper`  
 Upper and lower limits for the control. For `SetRange`, neither limit can be greater than **UD_MAXVAL** or less than **UD_MINVAL**; in addition, the difference between the two limits cannot exceed **UD_MAXVAL**. `SetRange32` places no restrictions on the limits; use any integers.  
  
### Remarks  
 The member function `SetRange32` sets the 32-bit range for the spin button control.  
  
> [!NOTE]
>  The default range for the spin button has the maximum set to zero (0) and the minimum set to 100. Because the maximum value is less than the minimum value, clicking the up arrow will decrease the position and clicking the down arrow will increase it. Use `CSpinButtonCtrl::SetRange` to adjust these values.  
  
## See Also  
 [MFC Sample CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd Class](../../mfc/reference/cwnd-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)

