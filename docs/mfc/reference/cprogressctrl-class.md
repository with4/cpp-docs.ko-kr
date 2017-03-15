---
title: "CProgressCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CProgressCtrl
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class
- progress controls [C++], CProgressCtrl class
- Internet Explorer 4.0 common controls
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
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
ms.openlocfilehash: 6c0e9bc16f88018c9f258504924670cc2be31d28
ms.lasthandoff: 02/24/2017

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
|[CProgressCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 진행률 컨트롤을 만들고에 연결 된 `CProgressCtrl` 개체입니다.|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|현재 진행률 표시줄 컨트롤에 대 한 진행률 표시줄의 색을 가져옵니다.|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|현재 진행률 표시줄의 배경색을 가져옵니다.|  
|[CProgressCtrl::GetPos](#getpos)|진행률 표시줄의 현재 위치를 가져옵니다.|  
|[CProgressCtrl::GetRange](#getrange)|아래쪽과 위쪽 제한을 진행률 표시줄 컨트롤의 범위를 가져옵니다.|  
|[CProgressCtrl::GetState](#getstate)|현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.|  
|[CProgressCtrl::GetStep](#getstep)|현재 진행률 표시줄 컨트롤의 진행률 표시줄에 대 한 단계적 증가 값을 검색합니다.|  
|[CProgressCtrl::OffsetPos](#offsetpos)|지정 된 증분만큼 진행률 표시줄 컨트롤의 현재 위치를 앞으로 이동 하 고 새 위치를 반영 하도록 막대를 다시 그립니다.|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|현재 진행률 표시줄 컨트롤의 진행률 표시줄의 색을 설정 합니다.|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|진행률 표시줄의 배경색을 설정합니다.|  
|[CProgressCtrl::SetMarquee](#setmarquee)|현재 진행률 표시줄 컨트롤에 대 한 움직이는 텍스트 모드 또는 해제를 설정합니다.|  
|[CProgressCtrl::SetPos](#setpos)|진행률 표시줄 컨트롤에 대 한 현재 위치를 설정 하 고 새 위치를 반영 하도록 막대를 다시 그립니다.|  
|[CProgressCtrl::SetRange](#setrange)|진행률 표시줄 컨트롤에 대 한 최소 및 최대 범위를 설정 하 고 새 범위를 반영 하도록 모음을 다시 그립니다.|  
|[CProgressCtrl::SetState](#setstate)|현재 진행률 표시줄 컨트롤의 상태를 설정합니다.|  
|[CProgressCtrl::SetStep](#setstep)|진행률 표시줄 컨트롤에 대 한 단계 증분 값을 지정 합니다.|  
|[CProgressCtrl::StepIt](#stepit)|진행률 표시줄 컨트롤에 대 한 현재 위치를 앞으로 이동 단계 증분만큼 (참조 [SetStep](#setstep)) 모음의 새 위치를 반영 하 고 다시 그립니다.|  
  
## <a name="remarks"></a>주의  
 진행률 표시줄 컨트롤에는 응용 프로그램은 긴 작업의 진행률을 표시 하는 데 사용할 수 있는 창입니다. 왼쪽부터 오른쪽, 시스템으로 강조 표시 색을 작업이 진행 됨에 따라 점진적으로 채워진 사각형으로 구성 됩니다.  
  
 진행률 표시줄 컨트롤에는 범위 및 현재 위치입니다. 범위 작업의 전체 지속 시간을 나타내며 현재 위치는 응용 프로그램은 작업 수행할 진행률을 나타냅니다. 창 프로시저 강조 색으로 채울 진행률 표시줄의 비율을 결정 하는 범위 및 현재 위치를 사용 합니다. 범위 및 현재 위치 값이 부호 있는 정수로 표현 되는 위치 값이 현재 가능한 범위 이므로에서 â €"2147483648과 2147483647 사이 (포함).  
  
 사용 하 여 대 한 자세한 내용은 `CProgressCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CProgressCtrl 사용 하 여](../../mfc/using-cprogressctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="a-namecprogressctrla--cprogressctrlcprogressctrl"></a><a name="cprogressctrl"></a>CProgressCtrl::CProgressCtrl  
 `CProgressCtrl` 개체를 생성합니다.  
  
```  
CProgressCtrl();
```  
  
### <a name="remarks"></a>주의  
 생성 한 후의 `CProgressCtrl` 개체, 호출 `CProgressCtrl::Create` 진행률 표시줄 컨트롤을 만들 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&1;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="a-namecreatea--cprogressctrlcreate"></a><a name="create"></a>CProgressCtrl::Create  
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
 진행률 표시줄 컨트롤의 스타일을 지정합니다. 창 stylesdescribed의 조합이 적용 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], 다음 진행률 표시줄 컨트롤에 컨트롤 스타일 외에도 합니다.  
  
- `PBS_VERTICAL`표시 정보를 세로 방향으로 진행, 위쪽에서 아래쪽입니다. 이 플래그가 없으면 진행률 표시줄 컨트롤 오른쪽 가로, 왼쪽으로 표시합니다.  
  
- `PBS_SMOOTH`진행률 표시줄 컨트롤을 채워 점진적 고 원활 하 게 표시 합니다. 이 플래그가 없으면 컨트롤은 블록으로 체 워 집니다.  
  
 `rect`  
 진행률 표시줄 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다. 클라이언트 영역을 기준으로 지정 된 좌표는 컨트롤 수 있어야 하므로 자식 창는 `pParentWnd`합니다.  
  
 `pParentWnd`  
 일반적으로 진행률 표시줄 컨트롤의 부모 창 지정을 `CDialog`합니다. 않아야 **NULL입니다.**  
  
 `nID`  
 진행률 표시줄 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 경우는 `CProgressCtrl` 성공적으로 생성 하 고 그렇지 않으면 개체는 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CProgressCtrl` 두 단계에서는 개체입니다. 첫째, 만듭니다 하는 생성자를 호출는 `CProgressCtrl` 개체를 다음 호출 **만들기**는 진행률 표시줄 컨트롤을 만듭니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&2;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="a-namecreateexa--cprogressctrlcreateex"></a><a name="createex"></a>CProgressCtrl::CreateEx  
 컨트롤 (자식 창)와 연결 된 `CProgressCtrl` 개체입니다.  
  
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
 진행률 표시줄 컨트롤의 스타일을 지정합니다. 에 설명 된 창 스타일의 조합이 적용 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
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
  
##  <a name="a-namegetbarcolora--cprogressctrlgetbarcolor"></a><a name="getbarcolor"></a>CProgressCtrl::GetBarColor  
 현재 진행률 표시줄 컨트롤에 대 한 진행률 표시줄의 색을 가져옵니다.  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 진행률 표시줄의 색으로 표시 한 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값 또는 `CLR_DEFAULT` 진행률 표시기 막대의 색은 기본 색 하는 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetbkcolora--cprogressctrlgetbkcolor"></a><a name="getbkcolor"></a>CProgressCtrl::GetBkColor  
 현재 진행률 표시줄의 배경색을 가져옵니다.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 진행률 표시줄의 배경색으로 표현 된 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetposa--cprogressctrlgetpos"></a><a name="getpos"></a>CProgressCtrl::GetPos  
 진행률 표시줄의 현재 위치를 검색합니다.  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 위치입니다.  
  
### <a name="remarks"></a>주의  
 진행률 표시줄 컨트롤의 위치는 화면에서 실제 위치 아니지만 대신 위에 사이 및 하 한 범위에 지정 된 [SetRange](#setrange)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&3;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="a-namegetrangea--cprogressctrlgetrange"></a><a name="getrange"></a>CProgressCtrl::GetRange  
 현재 아래쪽 및 위쪽 제한 또는 진행률 표시줄 컨트롤의 범위를 가져옵니다.  
  
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
  
### <a name="remarks"></a>주의  
 이 함수에서 참조 하는 정수를 아래쪽 및 위쪽 제한의 값을 복사 `nLower` 및 `nUpper`각각.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&4;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="a-namegetstatea--cprogressctrlgetstate"></a><a name="getstate"></a>CProgressCtrl::GetState  
 현재 진행률 표시줄 컨트롤의 상태를 가져옵니다.  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상태는 다음 값 중 하나는 현재 진행률 표시줄 컨트롤입니다.  
  
|값|상태|  
|-----------|-----------|  
|`PBST_NORMAL`|진행 중|  
|`PBST_ERROR`|오류|  
|`PBST_PAUSED`|일시 중지됨|  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 상태를 검색 합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&5;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="a-namegetstepa--cprogressctrlgetstep"></a><a name="getstep"></a>CProgressCtrl::GetStep  
 현재 진행률 표시줄 컨트롤의 진행률 표시줄에 대 한 단계적 증가 값을 검색합니다.  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄의 단계 증가 합니다.  
  
### <a name="remarks"></a>주의  
 단계 증분은 양입니다에 대 한 호출 [CProgressCtrl::StepIt](#stepit) 진행률 표시줄의 현재 위치를 증가 합니다.  
  
 이 메서드는 전송 된 [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 단계적 증가 값을 검색합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&3;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="a-nameoffsetposa--cprogressctrloffsetpos"></a><a name="offsetpos"></a>CProgressCtrl::OffsetPos  
 진행률 표시줄 컨트롤의 현재 위치를 앞으로 이동 하 여 지정 된 증분만큼 `nPos` 모음의 새 위치를 반영 하 고 다시 그립니다.  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 위치를 앞으로 이동 하는 양입니다.  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 이전 위치입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&5;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="a-namesetbarcolora--cprogressctrlsetbarcolor"></a><a name="setbarcolor"></a>CProgressCtrl::SetBarColor  
 현재 진행률 표시줄 컨트롤의 진행률 표시줄의 색을 설정 합니다.  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `clrBar`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 진행률 표시줄의 새로운 색을 지정 하는 값입니다. 지정 `CLR_DEFAULT` 기본 색을 사용 하 여 진행률 표시줄을 합니다.|  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄의 이전 색으로 표시 한 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값 또는 `CLR_DEFAULT` 진행률 표시줄의 색은 기본 색 하는 경우.  
  
### <a name="remarks"></a>주의  
 `SetBarColor` 진행률 표시줄 경우에만 색을 설정 하는 메서드는 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] [테마](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx) 적용 되지 않습니다.  
  
 이 메서드는 전송 된 [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 빨간색, 녹색, 파란색, 또는 기본값에 진행률 표시줄의 색을 변경합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="a-namesetbkcolora--cprogressctrlsetbkcolor"></a><a name="setbkcolor"></a>CProgressCtrl::SetBkColor  
 진행률 표시줄의 배경색을 설정합니다.  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `clrNew`  
 A **COLORREF** 새 배경 색을 지정 하는 값입니다. 지정 된 `CLR_DEFAULT` 진행률 표시줄에 대 한 기본 배경색을 사용 하는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 이전 배경색을 나타내는 값 또는 **CLR_DEFAULT** 배경색은 기본 색 하는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&6;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="a-namesetmarqueea--cprogressctrlsetmarquee"></a><a name="setmarquee"></a>CProgressCtrl::SetMarquee  
 현재 진행률 표시줄 컨트롤에 대 한 움직이는 텍스트 모드 또는 해제를 설정합니다.  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `fMarqueeMode`|`true`움직이는 텍스트 모드를 켜려면 또는 `false` 움직이는 텍스트 모드를 끕니다.|  
|[in] `nInterval`|움직이는 텍스트 애니메이션의 업데이트 간격 (밀리초) 시간입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 항상 `true`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 움직이는 텍스트 모드를 설정 하는 진행률 표시줄은 애니메이션이 적용 하 고 스크롤 같은 극장 움직이는 텍스트 로그온입니다.  
  
 이 메서드는 전송 된 [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 시작 하 고 움직이는 애니메이션을 중지 합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&2;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="a-namesetposa--cprogressctrlsetpos"></a><a name="setpos"></a>CProgressCtrl::SetPos  
 진행률 표시줄 컨트롤의 현재 위치에 지정 된 대로 설정 `nPos` 모음의 새 위치를 반영 하 고 다시 그립니다.  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 진행률 표시줄 컨트롤의 새 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 이전 위치입니다.  
  
### <a name="remarks"></a>주의  
 진행률 표시줄 컨트롤의 위치는 화면에서 실제 위치 아니지만 대신 위에 사이 및 하 한 범위에 지정 된 [SetRange](#setrange)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&7;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="a-namesetrangea--cprogressctrlsetrange"></a><a name="setrange"></a>CProgressCtrl::SetRange  
 진행률 표시줄 컨트롤의 범위 최대값과 최소값을 설정 하 고 새 범위를 반영 하도록 모음을 다시 그립니다.  
  
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
 범위의 하 한을 지정 (기본값은&0;).  
  
 `nUpper`  
 범위의 상한을 지정 (기본값은 100).  
  
### <a name="remarks"></a>주의  
 멤버 함수 `SetRange32` 진행률 컨트롤에 대 한 32 비트 범위를 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&8;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
##  <a name="a-namesetstatea--cprogressctrlsetstate"></a><a name="setstate"></a>CProgressCtrl::SetState  
 현재 진행률 표시줄 컨트롤의 상태를 설정합니다.  
  
```  
int SetState(int iState);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iState`|진행률 표시줄을 설정할 상태입니다. 다음 값 중 하나를 사용합니다.<br /><br /> - `PBST_NORMAL`-진행 중인<br />- `PBST_ERROR`-오류<br />- `PBST_PAUSED`-일시 중지|  
  
### <a name="return-value"></a>반환 값  
 현재 진행률 표시줄 컨트롤의 이전 상태입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 프로그래밍 방식으로 진행률 표시줄 컨트롤에 액세스하는 데 사용되는 `m_progressCtrl` 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 진행률 표시줄 컨트롤의 상태를 일시 중지됨 또는 진행 중으로 설정합니다.  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;&4;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="a-namesetstepa--cprogressctrlsetstep"></a><a name="setstep"></a>CProgressCtrl::SetStep  
 진행률 표시줄 컨트롤에 대 한 단계 증분 값을 지정 합니다.  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>매개 변수  
 *nStep*  
 새 단계 증가 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전 단계 증가 합니다.  
  
### <a name="remarks"></a>주의  
 단계 증분은 양입니다에 대 한 호출 `CProgressCtrl::StepIt` 증가 진행률 표시줄의 현재 위치입니다.  
  
 기본 단계 증가분은 10입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="a-namestepita--cprogressctrlstepit"></a><a name="stepit"></a>CProgressCtrl::StepIt  
 단계 증분만큼 진행률 표시줄 컨트롤에 대 한 현재 위치를 앞으로 이동 하 고 새 위치를 반영 하도록 막대를 다시 그립니다.  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>반환 값  
 진행률 표시줄 컨트롤의 이전 위치입니다.  
  
### <a name="remarks"></a>주의  
 의 단계 단위는 설정의 `CProgressCtrl::SetStep` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CProgressCtrl #&10;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



