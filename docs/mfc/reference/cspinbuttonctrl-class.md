---
title: CSpinButtonCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43b0967309813603e4f683f35c3ca51dce99fd8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374693"
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
|[CSpinButtonCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 스핀 단추 컨트롤을 만들고에 연결 된 `CSpinButtonCtrl` 개체입니다.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|스핀 단추 컨트롤에 대 한 가속 정보를 검색합니다.|  
|[CSpinButtonCtrl::GetBase](#getbase)|스핀 단추 컨트롤에 대 한 현재 자료를 검색합니다.|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|현재 버디 창에 대 한 포인터를 검색합니다.|  
|[CSpinButtonCtrl::GetPos](#getpos)|스핀 단추 컨트롤의 현재 위치를 검색합니다.|  
|[CSpinButtonCtrl::GetRange](#getrange)|스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 검색합니다.|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|스핀 단추 컨트롤에 대 한 가속을 설정합니다.|  
|[CSpinButtonCtrl::SetBase](#setbase)|스핀 단추 컨트롤을 설정 합니다.|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|스핀 단추 컨트롤의 버디 창을 설정입니다.|  
|[CSpinButtonCtrl::SetPos](#setpos)|컨트롤에 대 한 현재 위치를 설정합니다.|  
|[CSpinButtonCtrl::SetRange](#setrange)|스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 "스핀 단추 컨트롤" (up-down 컨트롤이 라고도 함)는 사용자를 증가 또는 감소 스크롤 위치 또는 도우미 컨트롤에 표시 되는 번호와 같은 값을 클릭할 수 있는 화살표 단추 쌍입니다. 스핀 단추 컨트롤에 연관 된 값의 현재 위치를 라고 합니다. 스핀 단추 컨트롤은 컨트롤과 함께, "버디 창입니다." 이라는 자주 사용 됩니다.  
  
 이 컨트롤 (및 따라서는 `CSpinButtonCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수는 있습니다.  
  
 사용자에 게 스핀 단추 컨트롤 및 버디 창 처럼 표시 됩니다는 단일 제어 합니다. 스핀 단추 컨트롤 자동으로 자체의 버디 창 옆에 놓고 자동으로 설정 있는지 버디 창의 캡션을 현재 위치를 지정할 수 있습니다. 숫자 입력에 대 한 사용자를 편집 컨트롤과 스핀 단추 컨트롤을 사용할 수 있습니다.  
  
 위쪽 화살표를 클릭 하면 현재 위치에서 최대 방향으로 이동한 최소 방향으로 현재 위치를 이동 아래쪽 화살표를 클릭 합니다. 기본적으로 최소값은 100이 고 최대값은 0입니다. 최소 설정 (예를 들어 기본 설정을 사용 될 때) 설정, 위쪽 화살표 감소를 클릭 하는 최대 길이 보다 큽니다. 언제 든 지 아래쪽 화살표를 클릭 하 고 위치 값 늘립니다.  
  
 스핀 단추 컨트롤 버디 창 없이 간소화 된 스크롤 막대의 정렬으로 작동합니다. 예를 들어 탭 컨트롤은 경우에 따라 추가 탭을 스크롤하여 볼 수 있도록 스핀 단추 컨트롤을 표시 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CSpinButtonCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CSpinButtonCtrl 사용 하 여](../../mfc/using-cspinbuttonctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="create"></a>  CSpinButtonCtrl::Create  
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
 Spin button 컨트롤 스타일을 지정합니다. 스핀 단추 컨트롤 스타일의 조합을 컨트롤에 적용 됩니다. 이러한 스타일에 설명 된 [Up-down 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759885) Windows sdk에서입니다.  
  
 `rect`  
 스핀 단추 컨트롤의 크기와 위치를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조  
  
 `pParentWnd`  
 스핀 단추 컨트롤의 부모 창, 일반적으로에 대 한 포인터는 `CDialog`합니다. 않아야 **NULL입니다.**  
  
 `nID`  
 스핀 단추 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 한 `CSpinButtonCtrl` 처음 두 단계에서 개체 생성자를 호출 하 고, 호출 하 **만들기**, 스핀 단추 컨트롤을 만들고에 연결는 `CSpinButtonCtrl` 개체입니다.  
  
 확장된 창 스타일을 사용 하 여 스핀 단추 컨트롤을 만들려면 호출 [CSpinButtonCtrl::CreateEx](#createex) 대신 **만들기**합니다.  
  
##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx  
 에 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CSpinButtonCtrl` 개체입니다.  
  
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
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 `dwStyle`  
 Spin button 컨트롤 스타일을 지정합니다. 스핀 단추 컨트롤 스타일의 조합을 컨트롤에 적용 됩니다. 이러한 스타일에 설명 된 [Up-down 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759885) Windows sdk에서입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_** 합니다.  
  
##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl  
 `CSpinButtonCtrl` 개체를 생성합니다.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel  
 스핀 단추 컨트롤에 대 한 가속 정보를 검색합니다.  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nAccel`  
 변수로 지정 된 배열에 있는 요소의 수 `pAccel`합니다.  
  
 `pAccel`  
 배열에 대 한 포인터 [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) 가속 정보를 수신 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 검색 된 액셀러레이터 키 구조체의 수입니다.  
  
##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase  
 스핀 단추 컨트롤에 대 한 현재 자료를 검색합니다.  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 기준 값입니다.  
  
##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy  
 현재 버디 창에 대 한 포인터를 검색합니다.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 버디 창에 대 한 포인터입니다.  
  
##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos  
 스핀 단추 컨트롤의 현재 위치를 검색합니다.  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *lpbError*  
 값 0으로 설정 하는 부울 값에 대 한 포인터 인지 성공적으로 검색 된 0이 아닌 경우 오류가 발생 합니다. 이 매개 변수 설정 하는 경우 **NULL**, 오류가 보고 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전 하위 단어에서 16 비트 현재 위치를 반환합니다. 상위 단어는 오류가 발생 한 경우 0이 아닌 값입니다.  
  
 두 번째 버전은 32 비트 위치를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 반환 되는 값을 처리할 때 컨트롤의 버디 창의 캡션을에 따라 현재 위치를 업데이트 합니다. 컨트롤의 버디 창이 없습니다 또는 캡션을 잘못 되었거나 범위를 벗어난 값을 지정 하는 경우 오류가 반환 됩니다.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 검색합니다.  
  
```  
DWORD GetRange() const;  
  
void GetRange(
    int& lower,  
    int& upper) const;  
  
void GetRange32(
    int& lower,  
    int &upper) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *더 낮은*  
 컨트롤에 대 한 하한값을 수신 하는 정수에 대 한 참조입니다.  
  
 *위쪽*  
 컨트롤에 대 한 상한값을 수신 하는 정수에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전에서 최대값과 최소값을 포함 하는 32 비트 값을 반환 합니다. 하위 단어는 컨트롤에 대 한 상한값 이며 번호 상위 하한값입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수 `GetRange32` 32 비트 정수로 스핀 단추 컨트롤의 범위를 검색 합니다.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 스핀 단추 컨트롤에 대 한 가속을 설정합니다.  
  
```  
BOOL SetAccel(
    int nAccel,  
    UDACCEL* pAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 `nAccel`  
 수가 [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) 구조에서 지정한 `pAccel`합니다.  
  
 `pAccel`  
 배열에 대 한 포인터 `UDACCEL` 가속 정보가 포함 된 구조입니다. 요소에 따라 오름차순으로 정렬할지는 **nSec** 멤버입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 스핀 단추 컨트롤을 설정 합니다.  
  
```  
int SetBase(int nBase);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBase`  
 컨트롤에 대 한 새 기준 값입니다. 10 진수에 대 한 10 또는 16 진수 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 이전 기준 값 이거나 잘못 된 base가 주어 지 면 0입니다.  
  
### <a name="remarks"></a>설명  
 기준 값 버디 창의 숫자 10 진수 또는 16 진수로 표시할지 여부를 결정 합니다. 16 진수 숫자는 항상 서명 합니다. 10 진수 서명 됩니다.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 스핀 단추 컨트롤의 버디 창을 설정입니다.  
  
```  
CWnd* SetBuddy(CWnd* pWndBuddy);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWndBuddy`  
 새 버디 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 버디 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 Spin 컨트롤 예: 일부 콘텐츠를 표시 하는 편집 컨트롤의 다른 창와 거의 항상 관련이 있습니다. 이 다른 창은 spin 컨트롤의 "버디" 라고 합니다.  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 스핀 단추 컨트롤에 대 한 현재 위치를 설정합니다.  
  
```  
int SetPos(int nPos);  
int SetPos32(int nPos);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 컨트롤에 대 한 새 위치입니다. 이 값은 컨트롤에 대 한 상한 및 하 한 제한으로 지정 된 범위에 있어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전 위치 (16 비트 전체 자릿수를 `SetPos`, 32 비트에 대 한 전체 자릿수 `SetPos32`).  
  
### <a name="remarks"></a>설명  
 `SetPos32` 32 비트 위치를 설정 합니다.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange  
 스핀 단추 컨트롤에 대 한 상한 및 하 한 제한 (범위)를 설정합니다.  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLower` 및 `nUpper`  
 컨트롤에 대 한 상한 및 하 한 제한입니다. 에 대 한 `SetRange`, 모두 제한 보다 클 수 **UD_MAXVAL** 또는 미만 **UD_MINVAL**; 또한의 차이 두 가지 제한 초과할 수 없습니다 **UD_MAXVAL**. `SetRange32` 제한;에 제한을 두지합니다 모든 정수를 사용 합니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수 `SetRange32` 스핀 단추 컨트롤에 대 한 32 비트 범위를 설정 합니다.  
  
> [!NOTE]
>  스핀 단추에 대 한 기본 범위에 영 (0)로 설정 하는 최대와 100으로 설정 하는 권한이 있습니다. 최대값은 최소값 보다 작을 이기 때문에 위쪽 화살표를 클릭 하면 위치 줄어들고 아래쪽 화살표를 클릭 하 고 증가 합니다. 사용 하 여 `CSpinButtonCtrl::SetRange` 이러한 값을 조정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl 클래스](../../mfc/reference/csliderctrl-class.md)
