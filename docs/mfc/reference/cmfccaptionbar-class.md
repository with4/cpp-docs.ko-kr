---
title: "CMFCCaptionBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionBar class
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c9be93449392de9d04e4869db8dcd73e08125c88
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar 클래스
A `CMFCCaptionBar` 개체는 세 가지 요소를 표시할 수 있는 컨트롤 막대를: 단추, 텍스트 레이블 및 비트맵입니다. 각 형식의 요소를 한 번에 하나만 표시할 수 있습니다. 각 요소를 컨트롤의 왼쪽 또는 오른쪽 가장자리나 가운데에 맞출 수 있습니다. 평면 또는 3D 스타일을 캡션 표시줄의 위쪽 및 아래쪽 테두리에 적용할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCCaptionBar::Create](#create)|캡션 표시줄 컨트롤을 만들고 연결 하는 `CMFCCaptionBar` 개체입니다.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|캡션 표시줄 및 부모 프레임 간에 다른 창을 동적으로 삽입할 수 있는지 여부를 나타냅니다. (재정의 [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|캡션 표시줄에 단추를 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|지정 된 요소의 맞춤을 반환 합니다.|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|캡션 표시줄의 테두리 크기를 반환합니다.|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|캡션 표시줄에 단추에 대 한 경계 사각형을 검색합니다.|  
|[CMFCCaptionBar::GetMargin](#getmargin)|캡션 표시줄 요소의 가장자리와의 캡션 표시줄 컨트롤의 가장자리 사이의 거리를 반환 합니다.|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|캡션 표시줄 메시지 표시줄 모드 인지 여부를 지정 합니다.|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|캡션 표시줄에서 비트맵 이미지를 제거합니다.|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|캡션 표시줄에서 단추를 제거합니다.|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|캡션 표시줄에서 아이콘을 제거 합니다.|  
|[CMFCCaptionBar::RemoveText](#removetext)|캡션 표시줄에서 텍스트 레이블을 제거합니다.|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|캡션 표시줄에 대 한 비트맵 이미지를 설정합니다.|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|캡션 표시줄의 테두리 크기를 설정합니다.|  
|[CMFCCaptionBar::SetButton](#setbutton)|캡션 표시줄에 대 한 단추를 설정합니다.|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|단추 누름 유지 여부를 지정 합니다.|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|단추에 대 한 도구 설명을 설정 합니다.|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|캡션 표시줄의 테두리 스타일을 설정합니다.|  
|[CMFCCaptionBar::SetIcon](#seticon)|캡션 표시줄에 대 한 아이콘을 설정합니다.|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|캡션 표시줄에 대 한 이미지에 대 한 도구 설명을 설정 합니다.|  
|[CMFCCaptionBar::SetMargin](#setmargin)|캡션 표시줄 요소의 가장자리와의 캡션 표시줄 컨트롤의 가장자리 사이의 거리를 설정합니다.|  
|[CMFCCaptionBar::SetText](#settext)|캡션 표시줄에 대 한 텍스트 레이블을 가져오거나 설정 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|캡션 표시줄의 배경을 채울 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|캡션 표시줄의 테두리를 그리는 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|캡션 표시줄 단추를 그릴 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|캡션 표시줄 이미지를 그릴 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|캡션 표시줄 텍스트를 그릴 프레임 워크에 의해 호출 됩니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|캡션 표시줄의 배경색입니다.|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|캡션 표시줄의 테두리 색입니다.|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|캡션 표시줄 텍스트의 색입니다.|  
  
## <a name="remarks"></a>주의  
 캡션 표시줄을 만들려면 다음이 단계를 따르십시오.  
  
1.  `CMFCCaptionBar` 개체를 생성합니다. 일반적으로 프레임 창 클래스의 캡션 표시줄을 추가 합니다.  
  
2.  호출 된 [CMFCCaptionBar::Create](#create) 캡션 표시줄 컨트롤을 만들고에 연결 하는 메서드는 `CMFCCaptionBar` 개체입니다.  
  
3.  호출 [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), 및 [CMFCCaptionBar::SetBitmap](#setbitmap) 캡션 표시줄 요소를 설정 합니다.  
  
 Button 요소를 설치할 때 단추의 명령 ID를 할당 해야 합니다. 캡션 표시줄 경로 단추를 클릭 하면는 `WM_COMMAND` 부모 프레임 창에이 ID가 있는 메시지입니다.  
  
 캡션 표시줄 수 Microsoft Office 2007 응용 프로그램에 표시 되는 메시지 표시줄을 에뮬레이션 하는 메시지 표시줄 모드 에서도 작동 합니다. 메시지 표시줄 모드에서의 캡션 표시줄 표시 비트맵, 메시지 및 된 단추 (일반적으로 대화 상자를 엽니다.) 비트맵에 도구 설명을 지정할 수 있습니다.  
  
 메시지 표시줄 모드를 사용 하려면 호출 [CMFCCaptionBar::Create](#create) 네 번째 매개 변수 (bIsMessageBarMode)를 설정 하 고 `TRUE`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCCaptionBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 캡션 표시줄 컨트롤을 만들고, 캡션 표시줄의 3D 테두리를 설정, 픽셀 단위로 캡션 표시줄 컨트롤의 가장자리와 요소 표시줄 캡션의 가장자리 사이의 거리를 설정, 캡션 표시줄에 대 한 단추를 설정, 단추에 대 한 도구 설명 설정, 캡션 표시줄에 대 한 텍스트 레이블을 설정합니다를 비트맵 이미지의 캡션 표시줄에 대 한 설정 을 캡션 표시줄에는 이미지에 대 한 도구 설명을 설정 합니다. 이 코드 조각은의 일부인는 [MS Office 2007 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo #&1;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo #&2;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcaptionbar.h  
  
##  <a name="create"></a>CMFCCaptionBar::Create  
 캡션 표시줄 컨트롤을 만들고 연결 하는 `CMFCCaptionBar` 개체입니다.  
  
```  
BOOL Create(
    DWORD dwStyle,  
    CWnd* pParentWnd,  
    UINT uID,  
    int nHeight=-1,  
    BOOL bIsMessageBarMode=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 캡션 표시줄 스타일의 논리 OR 조합입니다.  
  
 `pParentWnd`  
 캡션 표시줄 컨트롤의 부모 창입니다.  
  
 `uID`  
 캡션 표시줄 컨트롤의 ID입니다.  
  
 `nHeight`  
 픽셀의 캡션 표시줄 컨트롤의 높이입니다. -1 이면 높이 아이콘, 텍스트 및 캡션 표시줄 컨트롤을 표시 하는 단추의 높이 따라 계산 됩니다.  
  
 `bIsMessageBarMode`  
 `TRUE`캡션 표시줄 메시지 표시줄 모드인; 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`캡션 표시줄 컨트롤을 성공적으로 만든 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 생성 한 `CMFCCaptionBar` 두 단계에서는 개체입니다. 먼저 생성자를 호출 하 고 호출 하는 다음의 `Create` Windows 컨트롤을 만들고에 연결 하는 메서드는 `CMFCCaptionBar` 개체입니다.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore  
 캡션 표시줄 및 부모 프레임 간에 다른 창을 동적으로 삽입할 수 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `FALSE` 재정의 되지 않는 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="enablebutton"></a>CMFCCaptionBar::EnableButton  
 캡션 표시줄에 단추를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`단추를 사용할 수 있도록 `FALSE` 단추를 비활성화 하려면.  
  
##  <a name="getalignment"></a>CMFCCaptionBar::GetAlignment  
 지정 된 요소의 맞춤을 반환 합니다.  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `elem`  
 캡션 표시줄을 맞춤 검색할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 단추, 비트맵, 텍스트 또는 아이콘 같은 요소에 맞춥니다.  
  
### <a name="remarks"></a>주의  
 요소의 맞춤 값 중 하나일 수 있습니다.  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize  
 캡션 표시줄의 테두리 크기를 반환합니다.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 테두리의 픽셀 크기입니다.  
  
##  <a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect  
 캡션 표시줄에 단추에 대 한 경계 사각형을 검색합니다.  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 의 캡션 표시줄에 단추는 경계 사각형의 좌표를 포함 하는 개체입니다.  
  
##  <a name="getmargin"></a>CMFCCaptionBar::GetMargin  
 캡션 표시줄 요소의 가장자리와의 캡션 표시줄 컨트롤의 가장자리 사이의 거리를 반환 합니다.  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 캡션 표시줄 요소의 가장자리와의 캡션 표시줄 컨트롤의 가장자리 사이의 거리입니다.  
  
##  <a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode  
 캡션 표시줄 메시지 표시줄 모드 인지 여부를 지정 합니다.  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`캡션 표시줄 메시지 표시줄 모드인; 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 메시지 표시줄 모드의 캡션 표시줄 도구 설명, 메시지 텍스트 및 단추를 사용 하 여 이미지를 표시합니다.  
  
##  <a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground  
 캡션 표시줄의 배경색입니다.  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder  
 캡션 표시줄의 테두리 색입니다.  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText  
 캡션 표시줄 텍스트의 색입니다.  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground  
 캡션 표시줄의 배경을 채울 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 캡션 표시줄의 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `rect`  
 경계 사각형 채우기입니다.  
  
### <a name="remarks"></a>주의  
 `OnDrawBackground` 캡션 표시줄의 배경을 채울 수 되려고 할 때 메서드가 호출 됩니다. 기본 구현에서는 사용 하 여 배경을 채우는 [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) 색입니다.  
  
 이 메서드를 재정의 하는 `CMFCCaptionBar` 캡션 표시줄의 모양을 사용자 지정 하는 클래스를 파생 합니다.  
  
##  <a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder  
 캡션 표시줄의 테두리를 그리는 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 테두리를 표시 하는 데 사용 되는 장치 컨텍스트.  
  
 [in] `rect`  
 경계 사각형입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 테두리 평면 스타일을 적용 합니다.  
  
 이 메서드를 재정의 하는 `CMFCCaptionBar` 의 캡션 표시줄의 테두리 모양을 사용자 지정 하는 클래스를 파생 합니다.  
  
##  <a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton  
 캡션 표시줄 단추를 그릴 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추를 표시 하는 데 사용 되는 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `rect`  
 단추는 경계 사각형입니다.  
  
 [in] `strButton`  
 단추의 텍스트 레이블입니다.  
  
 [in] `bEnabled`  
 `TRUE`단추가 활성화 됩니다. `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드를 재정의 하는 `CMFCCaptionBar` 의 캡션 표시줄의 단추 모양을 사용자 지정 하는 클래스를 파생 합니다.  
  
##  <a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage  
 캡션 표시줄 이미지를 그릴 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 이미지를 표시 하는 데 사용 되는 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `rect`  
 이미지의 경계 사각형을 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 재정의 하는 `CMFCCaptionBar` 이미지 모양을 사용자 지정 하는 클래스를 파생 합니다.  
  
##  <a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText  
 캡션 표시줄 텍스트를 그릴 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추를 표시 하는 데 사용 되는 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `rect`  
 텍스트의 경계 사각형입니다.  
  
 [in] `strText`  
 표시할 텍스트 문자열입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 텍스트를 표시 하는 기본 구현은 `CDC::DrawText` 및 [CMFCCaptionBar::m_clrBarText](#m_clrbartext) 색입니다.  
  
 이 메서드를 재정의 하는 `CMFCCaptionBar` 캡션 표시줄 텍스트의 모양을 사용자 지정 하는 클래스를 파생 합니다.  
  
##  <a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap  
 캡션 표시줄에서 비트맵 이미지를 제거합니다.  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>CMFCCaptionBar::RemoveButton  
 캡션 표시줄에서 단추를 제거합니다.  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>주의  
 캡션 표시줄 요소의 레이아웃은 자동으로 조정 됩니다.  
  
##  <a name="removeicon"></a>CMFCCaptionBar::RemoveIcon  
 캡션 표시줄에서 아이콘을 제거 합니다.  
  
```  
void RemoveIcon();
```  
  
##  <a name="removetext"></a>CMFCCaptionBar::RemoveText  
 캡션 표시줄에서 텍스트 레이블을 제거합니다.  
  
```  
void RemoveText();
```  
  
##  <a name="setbitmap"></a>CMFCCaptionBar::SetBitmap  
 캡션 표시줄에 대 한 비트맵 이미지를 설정합니다.  
  
```  
void SetBitmap(
    HBITMAP hBitmap,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

 
void SetBitmap(
    UINT uiBmpResID,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hBitmap`  
 핸들을 설정 하는 비트맵입니다.  
  
 [in] `clrTransparent`  
 비트맵의 투명 한 색을 지정 하는 RGB 값입니다.  
  
 [in] `bStretch`  
 경우 `TRUE`, 비트맵 이미지 경계 사각형에 맞지 않을 경우 연장 됩니다. 그렇지 않으면 비트맵 늘어나지 않습니다.  
  
 [in] `bmpAlignment`  
 비트맵의 맞춤입니다.  
  
### <a name="remarks"></a>주의  
 캡션 표시줄에 비트맵을 설정 하려면이 메서드를 사용 합니다.  
  
 이전 비트맵은 자동으로 소멸 됩니다. 호출 하기 때문에 캡션 표시줄 아이콘을 표시 하는 경우는 [CMFCCaptionBar::SetIcon](#seticon) 메서드를 호출 하 여 아이콘을 제거 하지 않으면 비트맵 표시 되지 것입니다 [CMFCCaptionBar::RemoveIcon](#removeicon)합니다.  
  
 비트맵은 정렬에 지정 된 대로 `bmpAlignment` 매개 변수입니다.  이 매개 변수는 다음 `BarElementAlignment` 값 중 하나일 수 있습니다.  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize  
 캡션 표시줄의 테두리 크기를 설정합니다.  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nSize`  
 캡션 표시줄 테두리를 픽셀 단위로 새 크기입니다.  
  
##  <a name="setbutton"></a>CMFCCaptionBar::SetButton  
 캡션 표시줄에 대 한 단추를 설정합니다.  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszLabel`  
 단추의 명령 레이블입니다.  
  
 `uiCmdUI`  
 단추의 명령 id입니다.  
  
 `btnAlignmnet`  
 단추의 맞춤입니다.  
  
 `bHasDropDownArrow`  
 `TRUE`단추는 드롭다운 화살표를 표시 하는 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed  
 단추 누름 유지 여부를 지정 합니다.  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bPresed`  
 `TRUE`단추를 누른된 상태로 유지 하는 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip  
 단추에 대 한 도구 설명을 설정 합니다.  
  
```  
void SetButtonToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszToolTip`  
 도구 설명 캡션입니다.  
  
 [in] `lpszDescription`  
 도구 설명에 대 한 설명입니다.  
  
##  <a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder  
 캡션 표시줄의 테두리 스타일을 설정합니다.  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bFlat`  
 `TRUE`캡션 표시줄의 테두리 플랫 경우 사용 됩니다. `FALSE`3D 테두리 경우.  
  
##  <a name="seticon"></a>CMFCCaptionBar::SetIcon  
 캡션 표시줄에 대 한 아이콘을 설정합니다.  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hIcon`  
 설정에 있는 아이콘에 대 한 핸들입니다.  
  
 [in] `iconAlignment`  
 아이콘의 맞춤입니다.  
  
### <a name="remarks"></a>주의  
 캡션 표시줄 아이콘 또는 비트맵을 표시할 수 있습니다. 참조 [CMFCCaptionBar::SetBitmap](#setbitmap) 비트맵을 표시 하는 방법을 알아볼 수 있습니다. 아이콘과 비트맵을 모두 설정 하면 아이콘이 표시 됩니다. 호출 [CMFCCaptionBar::RemoveIcon](#removeicon) 캡션 표시줄에서 아이콘을 제거 하려면.  
  
 아이콘에 따라 정렬 되는 `iconAlignment` 매개 변수입니다. 다음 중 하나일 수 있습니다 `BarElementAlignment` 값:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip  
 캡션 표시줄에는 이미지에 대 한 도구 설명을 설정합니다.  
  
```  
void SetImageToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszToolTip`  
 도구 설명의 텍스트입니다.  
  
 [in] `lpszDescription`  
 도구 설명에 대 한 설명입니다.  
  
##  <a name="setmargin"></a>CMFCCaptionBar::SetMargin  
 캡션 표시줄 요소의 가장자리와의 캡션 표시줄 컨트롤의 가장자리 사이의 거리를 설정합니다.  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nMargin`  
 픽셀 단위로 캡션 표시줄 요소의 가장자리와의 캡션 표시줄 컨트롤의 가장자리 사이의 거리입니다.  
  
##  <a name="settext"></a>CMFCCaptionBar::SetText  
 캡션 표시줄에 대 한 텍스트 레이블을 가져오거나 설정 합니다.  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strText`  
 설정 하려면 텍스트 문자열입니다.  
  
 [in] `textAlignment`  
 텍스트 맞춤입니다.  
  
### <a name="remarks"></a>주의  
 텍스트 레이블을 맞춥니다에 지정 된 대로 `textAlignment` 매개 변수입니다. 다음 중 하나일 수 있습니다 `BarElementAlignment` 값:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

