---
title: CProgressCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6317ce9484cc471611762d10e6f1482f24c2742a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cprogressctrl-class"></a>CProgressCtrl 클래스
Windows의 공용 진행률 표시줄 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|`CProgressCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CProgressCtrl::Create](#create)|진행률 표시줄 컨트롤을 만들고이에 연결 된 `CProgressCtrl` 개체입니다.|  
|[CProgressCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 진행률 컨트롤을 만들고에 연결 된 `CProgressCtrl` 개체입니다.|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|현재 진행률 표시줄 컨트롤에 대 한 진행률 표시줄의 색을 가져옵니다.|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|현재 진행률 표시줄의 배경색을 가져옵니다.|  
|[CProgressCtrl::GetPos](#getpos)|진행률 표시줄의 현재 위치를 가져옵니다.|  
|[CProgressCtrl::GetRange](#getrange)|진행률 표시줄 컨트롤의 범위 아래쪽과 위쪽 제한을 가져옵니다.|  
|[Cprogressctrl:: Getstate](#getstate)|현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.|  
|[CProgressCtrl::GetStep](#getstep)|진행률 표시줄의 현재 진행률 표시줄 컨트롤에 대 한 단계 증가값을 검색합니다.|  
|[CProgressCtrl::OffsetPos](#offsetpos)|지정 된 증분만큼 진행률 표시줄 컨트롤의 현재 위치를 앞으로 이동 하 고 새 위치를 반영 하도록 표시줄을 다시 그립니다.|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|현재 진행률 표시줄 컨트롤에서 진행률 표시줄의 색을 설정합니다.|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|진행률 표시줄의 배경색을 설정합니다.|  
|[CProgressCtrl::SetMarquee](#setmarquee)|현재 진행률 표시줄 컨트롤에 대 한 움직이는 텍스트 모드를 끄거나를 설정합니다.|  
|[CProgressCtrl::SetPos](#setpos)|진행률 표시줄 컨트롤에 대 한 현재 위치를 설정 하 고 새 위치를 반영 하도록 표시줄을 다시 그립니다.|  
|[CProgressCtrl::SetRange](#setrange)|진행률 표시줄 컨트롤에 대 한 최소 및 최대 범위를 설정 하 고 새 범위를 반영 하기 위해 막대를 다시 그립니다.|  
|[CProgressCtrl::SetState](#setstate)|현재 진행률 표시줄 컨트롤의 상태를 설정합니다.|  
|[CProgressCtrl::SetStep](#setstep)|진행률 표시줄 컨트롤에 대 한 단계 증분 값을 지정 합니다.|  
|[CProgressCtrl::StepIt](#stepit)|단계 증분만큼 진행률 표시줄 컨트롤에 대 한 현재 위치를 앞으로 이동 (참조 [SetStep](#setstep)) 모음의 새 위치를 반영 하 고 다시 그립니다.|  
  
## <a name="remarks"></a>설명  
 진행률 표시줄 컨트롤에는 응용 프로그램은 긴 작업의 진행률을 표시 하는 데 사용할 수 있는 창입니다. 왼쪽에서 오른쪽, 시스템 강조 색 작업이 진행 됨에 따라 점진적으로 채워진 사각형 구성 됩니다.  
  
 진행률 표시줄 컨트롤에는 범위와 현재 위치입니다. 범위는 작업의 총 기간을 나타내는 및 현재 위치는 응용 프로그램은 작업 수행할 진행률을 나타냅니다. 창 프로시저를 사용 하 여 범위 및 현재 위치는 진행률 표시줄의 강조 색으로 채울 수의 비율을 확인 합니다. 범위 및 현재 위치 값 부호 있는 정수로 표현 되는 가능한 값 범위를 현재 위치 되므로-2147483648에서 2147483647 까지입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CProgressCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CProgressCtrl 사용 하 여](../../mfc/using-cprogressctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl  
 `CProgressCtrl` 개체를 생성합니다.  
  
```  
CProgressCtrl();
```  
  
### <a name="remarks"></a>설명  
 생성 한 후의 `CProgressCtrl` 개체, 호출 `CProgressCtrl::Create` 진행률 표시줄 컨트롤을 만들 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="create"></a>  CProgressCtrl::Create  
 진행률 표시줄 컨트롤을 만들고이에 연결 된 `CProgressCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 진행률 표시줄 컨트롤의 스타일을 지정합니다. 어떠한 조합의에 창 stylesdescribed 적용 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 다음 진행률 표시줄 컨트롤에 컨트롤 스타일 외에도 Windows SDK에서:  
  
- `PBS_VERTICAL` 표시 정보를 세로로 진행, 위쪽에서 아래쪽입니다. 이 플래그가 없으면 진행률 표시줄 컨트롤이 표시 가로로, 왼쪽에서 오른쪽 됩니다.  
  
- `PBS_SMOOTH` 진행률 표시줄 컨트롤이 점진적, 부드러운 입력을 표시 합니다. 이 플래그가 없으면 블록으로 컨트롤을 채웁니다.  
  
 `rect`  
 진행률 표시줄 컨트롤의 크기와 위치를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다. 클라이언트 영역을 기준으로 지정 된 좌표는 컨트롤을 자식 창와 있어야 하므로 `pParentWnd`합니다.  
  
 `pParentWnd`  
 진행률 표시줄 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL입니다.**  
  
 `nID`  
 진행률 표시줄 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 경우는 `CProgressCtrl` 개체는 성공적으로, 그러지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CProgressCtrl` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출을 만드는 `CProgressCtrl` 개체를 호출 합니다 **만들기**, 진행률 표시줄 컨트롤이 만듭니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CProgressCtrl::CreateEx  
 에 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CProgressCtrl` 개체입니다.  
  
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
 진행률 표시줄 컨트롤의 스타일을 지정합니다. 에 설명 된 창 스타일의 조합을 적용 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows sdk에서입니다.  
  
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
  
##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor  
 현재 진행률 표시줄 컨트롤에 대 한 진행률 표시줄의 색을 가져옵니다.  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 진행률 표시줄의 색으로 표시 한 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값 또는 `CLR_DEFAULT` 진행률 표시기 막대의 색은 기본 색 하는 경우.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor  
 현재 진행률 표시줄의 배경색을 가져옵니다.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 진행률 표시줄의 배경색으로 표현 된 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getpos"></a>  CProgressCtrl::GetPos  
 진행률 표시줄의 현재 위치를 검색합니다.  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 위치입니다.  
  
### <a name="remarks"></a>설명  
 진행률 표시줄 컨트롤의 위치, 화면의 실제 위치 하지만 대신 위 사이 및 하 한 범위 ´ ֲ ְ [SetRange](#setrange)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="getrange"></a>  CProgressCtrl::GetRange  
 현재 아래쪽과 위쪽 제한 또는 진행률 표시줄 컨트롤의 범위를 가져옵니다.  
  
```  
void GetRange(
    int& nLower,  
    int& nUpper);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLower`  
 진행률 표시줄 컨트롤의 하 한을 수신 하는 정수에 대 한 참조입니다.  
  
 `nUpper`  
 진행률 표시줄 컨트롤의 상한값을 수신 하는 정수에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 참조 하는 정수에는 정수 제한 값을 복사 `nLower` 및 `nUpper`각각.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="getstate"></a>  Cprogressctrl:: Getstate  
 현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상태는 다음 값 중 하나는 현재 진행률 표시줄 컨트롤입니다.  
  
|값|시스템 상태|  
|-----------|-----------|  
|`PBST_NORMAL`|진행 중|  
|`PBST_ERROR`|Error|  
|`PBST_PAUSED`|일시 중지됨|  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 상태를 검색 합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="getstep"></a>  CProgressCtrl::GetStep  
 진행률 표시줄의 현재 진행률 표시줄 컨트롤에 대 한 단계 증가값을 검색합니다.  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄의 단계 증가 합니다.  
  
### <a name="remarks"></a>설명  
 단계 증가값은 양입니다에 대 한 호출 [CProgressCtrl::StepIt](#stepit) 진행률 표시줄의 현재 위치를 증가 합니다.  
  
 이 메서드는 전송 된 [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 단계적 증가 값을 검색합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos  
 진행률 표시줄 컨트롤의 현재 위치를 앞으로 이동 하 여 지정 된 증분만큼 `nPos` 모음의 새 위치를 반영 하 고 다시 그립니다.  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 위치를 이동 하는 양입니다.  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 이전 위치입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor  
 현재 진행률 표시줄 컨트롤에서 진행률 표시줄의 색을 설정합니다.  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `clrBar`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 진행률 표시줄의 새로운 색을 지정 하는 값입니다. 지정 `CLR_DEFAULT` 기본 색을 사용 하는 진행률 표시줄을 발생할 수 있습니다.|  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄의 이전 색으로 표시는 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값 또는 `CLR_DEFAULT` 경우 진행률 표시줄의 색은 기본 색입니다.  
  
### <a name="remarks"></a>설명  
 `SetBarColor` 진행률 표시줄 경우에만 색을 설정 하는 메서드는 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] [테마](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx) 은 적용 되지 않습니다.  
  
 이 메서드는 전송 된 [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 빨간색, 녹색, 파란색, 또는 기본값을 진행률 표시줄의 색을 변경합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor  
 진행률 표시줄의 배경색을 설정합니다.  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `clrNew`  
 A **COLORREF** 새 배경 색을 지정 하는 값입니다. 지정 된 `CLR_DEFAULT` 진행률 표시줄에 대 한 기본 배경색을 사용 하는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 이전 배경색을 나타내는 값 또는 **CLR_DEFAULT** 배경 색은 기본 색 하는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee  
 현재 진행률 표시줄 컨트롤에 대 한 움직이는 텍스트 모드를 끄거나를 설정합니다.  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `fMarqueeMode`|`true` 움직이는 텍스트 모드를 켜려면 또는 `false` 움직이는 텍스트 모드를 끕니다.|  
|[in] `nInterval`|움직이는 텍스트 애니메이션의 한 업데이트 간격 (밀리초)에 대 한 시간입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 항상 `true`을 반환합니다.  
  
### <a name="remarks"></a>설명  
 움직이는 텍스트 모드가 설정 하 고 진행률 표시줄에 애니메이션 효과가 적용 되어 스크롤 같은 극장식 움직이는 텍스트 로그온입니다.  
  
 이 메서드는 전송 된 [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 시작 되 고 애니메이션 움직이는 중지 합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="setpos"></a>  CProgressCtrl::SetPos  
 진행률 표시줄 컨트롤의 현재 위치에 지정 된 대로 설정 `nPos` 모음의 새 위치를 반영 하 고 다시 그립니다.  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 진행률 표시줄 컨트롤의 새 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 이전 위치입니다.  
  
### <a name="remarks"></a>설명  
 진행률 표시줄 컨트롤의 위치, 화면의 실제 위치 하지만 대신 위 사이 및 하 한 범위 ´ ֲ ְ [SetRange](#setrange)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="setrange"></a>  CProgressCtrl::SetRange  
 진행률 표시줄 컨트롤의 범위의 상한 및 하 한 제한을 설정 하 고 새 범위를 반영 하기 위해 막대를 다시 그립니다.  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLower`  
 범위의 하한값을 지정 (기본값은 0).  
  
 `nUpper`  
 범위의 상한을 지정 (기본값은 100).  
  
### <a name="remarks"></a>설명  
 멤버 함수 `SetRange32` 는 진행률 컨트롤에 대 한 32 비트 범위를 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
##  <a name="setstate"></a>  CProgressCtrl::SetState  
 현재 진행률 표시줄 컨트롤의 상태를 설정합니다.  
  
```  
int SetState(int iState);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iState`|진행률 표시줄을 설정할 상태입니다. 다음 값 중 하나를 사용합니다.<br /><br /> - `PBST_NORMAL` -진행 중인<br />- `PBST_ERROR` -오류<br />- `PBST_PAUSED` -일시 중지|  
  
### <a name="return-value"></a>반환 값  
 현재 진행률 표시줄 컨트롤의 이전 상태입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 상태를 일시 중지됨 또는 진행 중으로 설정합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="setstep"></a>  CProgressCtrl::SetStep  
 진행률 표시줄 컨트롤에 대 한 단계 증분 값을 지정 합니다.  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>매개 변수  
 *nStep*  
 새 단계 증가 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전 단계 증가 합니다.  
  
### <a name="remarks"></a>설명  
 단계 증가값은 양입니다에 대 한 호출 `CProgressCtrl::StepIt` 증가 진행률 표시줄의 현재 위치입니다.  
  
 기본 단계 증가분은 10입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="stepit"></a>  CProgressCtrl::StepIt  
 단계 증분만큼 진행률 표시줄 컨트롤에 대 한 현재 위치를 앞으로 이동 하 고 새 위치를 반영 하도록 표시줄을 다시 그립니다.  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 이전 위치입니다.  
  
### <a name="remarks"></a>설명  
 의 단계 단위는 설정의 `CProgressCtrl::SetStep` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)


