---
title: CButton 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
dev_langs:
- C++
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e232c363da4c9bbaf7e049551f9e2915671098c
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957444"
---
# <a name="cbutton-class"></a>CButton 클래스
Windows 단추 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CButton : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CButton::CButton](#cbutton)|`CButton` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CButton::Create](#create)|Windows 단추 컨트롤을 만들고에 연결 된 `CButton` 개체입니다.|  
|[CButton::DrawItem](#drawitem)|소유자가 그린 그리려는 재정의 `CButton` 개체입니다.|  
|[CButton::GetBitmap](#getbitmap)|이전에 사용 하 여 설정 하는 비트맵의 핸들을 검색 [SetBitmap](#setbitmap)합니다.|  
|[CButton::GetButtonStyle](#getbuttonstyle)|단추 컨트롤의 스타일에 대 한 정보를 검색합니다.|  
|[CButton::GetCheck](#getcheck)|단추 컨트롤의 선택 상태를 검색합니다.|  
|[CButton::GetCursor](#getcursor)|검색으로 이전에 설정 된 커서 이미지 핸들 [SetCursor](#setcursor)합니다.|  
|[CButton::GetIcon](#geticon)|이전에 사용 하 여 설정 아이콘의 핸들을 검색 [SetIcon](#seticon)합니다.|  
|[CButton::GetIdealSize](#getidealsize)|단추 컨트롤의 이상적인 크기를 검색합니다.|  
|[CButton::GetImageList](#getimagelist)|단추 컨트롤의 이미지 목록을 검색합니다.|  
|[CButton::GetNote](#getnote)|현재 명령 링크 컨트롤의 참고 구성 요소를 검색합니다.|  
|[CButton::GetNoteLength](#getnotelength)|현재 명령 링크 컨트롤에 대 한 주석 텍스트의 길이 검색합니다.|  
|[CButton::GetSplitGlyph](#getsplitglyph)|현재는 분할 단추 컨트롤과 관련 된 문자를 검색 합니다.|  
|[CButton::GetSplitImageList](#getsplitimagelist)|현재 분할 단추 컨트롤에 대 한 이미지 목록을 검색합니다.|  
|[CButton::GetSplitInfo](#getsplitinfo)|현재 분할 단추 컨트롤을 정의 하는 정보를 검색 합니다.|  
|[CButton::GetSplitSize](#getsplitsize)|현재는 분할 단추 컨트롤의 드롭다운 목록 구성 요소의 경계 사각형을 검색 합니다.|  
|[CButton::GetSplitStyle](#getsplitstyle)|현재 분할 단추 컨트롤을 정의 하는 분할 단추 스타일을 검색 합니다.|  
|[CButton::GetState](#getstate)|상태 확인, 강조 표시 상태 및 단추 컨트롤의 포커스 상태를 검색합니다.|  
|[CButton::GetTextMargin](#gettextmargin)|단추 컨트롤의 텍스트 여백을 검색합니다.|  
|[CButton::SetBitmap](#setbitmap)|단추에 표시할 비트맵을 지정 합니다.|  
|[CButton::SetButtonStyle](#setbuttonstyle)|Button의 스타일을 변경합니다.|  
|[CButton::SetCheck](#setcheck)|단추 컨트롤의 선택 상태를 설정합니다.|  
|[CButton::SetCursor](#setcursor)|단추에 표시할 커서 이미지를 지정 합니다.|  
|[CButton::SetDropDownState](#setdropdownstate)|현재는 분할 단추 컨트롤의 드롭 다운 상태를 설정합니다.|  
|[CButton::SetIcon](#seticon)|단추에 표시할 아이콘을 지정 합니다.|  
|[CButton::SetImageList](#setimagelist)|단추 컨트롤의 이미지 목록을 설정합니다.|  
|[CButton::SetNote](#setnote)|현재 명령 링크 컨트롤에 메모를 설정합니다.|  
|[CButton::SetSplitGlyph](#setsplitglyph)|현재 분할 단추 컨트롤을 지정 된 문자 모양에 연결합니다.|  
|[CButton::SetSplitImageList](#setsplitimagelist)|현재 분할 단추 컨트롤 이미지 목록에 연결합니다.|  
|[CButton::SetSplitInfo](#setsplitinfo)|현재 분할 단추 컨트롤을 정의 하는 정보를 지정 합니다.|  
|[CButton::SetSplitSize](#setsplitsize)|현재는 분할 단추 컨트롤의 드롭다운 목록 구성 요소의 경계 사각형을 설정합니다.|  
|[CButton::SetSplitStyle](#setsplitstyle)|현재 분할 단추 컨트롤의 스타일을 설정 합니다.|  
|[CButton::SetState](#setstate)|단추 컨트롤의 강조 표시 상태를 설정합니다.|  
|[CButton::SetTextMargin](#settextmargin)|단추 컨트롤의 텍스트 여백을 설정입니다.|  
  
## <a name="remarks"></a>설명  
 단추 컨트롤은 켜고 클릭할 수 있는 작은 사각형 자식 창. 단추에서 사용할 수 있습니다 및 하거나 레이블을 지정할 수 있습니다 또는 텍스트 없이 표시 합니다. 단추 클릭 모양을 일반적으로 변경 합니다.  
  
 일반적인 단추는 확인란, 라디오 단추 및 누름 단추입니다. A `CButton` , 이러한 개체가 될 수 있습니다에 따라는 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles) 하 여 초기화에서 지정 된는 [만들기](#create) 멤버 함수입니다.  
  
 또한는 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) 에서 파생 된 클래스 `CButton` 텍스트가 아닌 비트맵 이미지로 레이블이 표시 된 단추 컨트롤의 생성을 지원 합니다. A `CBitmapButton` 단추의, 아래쪽, 치중 하 고 상태를 사용 하지 않도록 설정에 대 한 별도 비트맵을 가질 수 있습니다.  
  
 대화 상자 템플릿에서 또는 코드에서 직접 단추 컨트롤을 만들 수 있습니다. 두 경우 모두 먼저 생성자 호출 `CButton` 생성 하는 `CButton` 호출; 개체는 `Create` 멤버 함수를 만들려면 Windows 단추 컨트롤에 연결 하 고는 `CButton` 개체입니다.  
  
 생성에서 파생 된 클래스에서 프로세스인 수 `CButton`합니다. 생성자는 파생된 클래스와 호출에 대 한 작성 `Create` 에서 생성자 내에서.  
  
 단추 컨트롤에서 보냅니다. 해당 부모에 Windows 알림 메시지를 처리 하려는 경우 (일반적으로 클래스에서 파생 [CDialog](../../mfc/reference/cdialog-class.md)), 각 메시지에 대 한 부모 클래스에는 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 항목은 다음 형식을 사용 합니다.  
  
 **ON_** 알림 **(**`id`, `memberFxn` **)**  
  
 여기서 `id` 알림을 전송 하는 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 한 부모 멤버 함수의 이름입니다.  
  
 부모의 함수 프로토타입에 다음과 같습니다.  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 메시지 맵 항목은 다음과 같습니다.  
  
|맵 항목|부모 시기를 전송 하는 중...|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|사용자가 단추를 클릭 합니다.|  
|**ON_BN_DOUBLECLICKED**|사용자가 단추를 두 번 클릭 합니다.|  
  
 만드는 경우는 `CButton` 대화 상자 리소스에서 개체는 `CButton` 개체는 사용자가 대화 상자를 닫을 때 자동으로 제거 됩니다.  
  
 만드는 경우는 `CButton` 개체 창으로 삭제 해야 할 수 있습니다. 만드는 경우는 `CButton` 개체를 사용 하 여 힙에 **새** 함수를 호출한 다음 **삭제** 개체에서 사용자가 창의 닫을 때 삭제를 단추 컨트롤입니다. 만드는 경우는 `CButton` 스택의 이거나에 개체가 부모 대화 상자 개체에 포함 된, 자동으로 삭제 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cbutton"></a>  CButton::CButton  
 `CButton` 개체를 생성합니다.  
  
```  
CButton();
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="create"></a>  CButton::Create  
 Windows 단추 컨트롤을 만들고에 연결 된 `CButton` 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszCaption*  
 단추 컨트롤의 텍스트를 지정합니다.  
  
 *dwStyle*  
 단추 컨트롤의 스타일을 지정합니다. 어떠한 조합의 적용 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles) 단추에 있습니다.  
  
 *rect*  
 단추 컨트롤의 크기와 위치를 지정합니다. 있습니다는 `CRect` 개체 또는 `RECT` 구조입니다.  
  
 *pParentWnd*  
 단추 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL**합니다.  
  
 *nID*  
 단추 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CButton` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출 하 고 호출 `Create`, Windows 단추 컨트롤을 만들고에 연결는 `CButton` 개체입니다.  
  
 경우는 **WS_VISIBLE** 스타일은 지정, Windows 단추 컨트롤 활성화 하 고 단추를 표시 하는 데 필요한 모든 메시지를 보냅니다.  
  
 다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 단추 컨트롤에:  
  
- **WS_CHILD** 항상  
  
- **WS_VISIBLE** Usually  
  
- **WS_DISABLED** 거의  
  
- **WS_GROUP** 컨트롤을 그룹화  
  
- **WS_TABSTOP** 탭 이동 순서에 있는 단추를 포함 하려면  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="drawitem"></a>  CButton::DrawItem  
 소유자가 그린 단추의 시각적 측면이 변경 될 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpDrawItemStruct*  
 에 대 한 긴 포인터는 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) 구조입니다. 구조에 필요한 그리기의 형식과 항목을 그릴 수 있도록 하는 방법에 대 한 정보가 들어 있습니다.  
  
### <a name="remarks"></a>설명  
 소유자가 그린 단추에는 **BS_OWNERDRAW** 스타일을 설정 합니다. 소유자가 그린에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CButton` 개체입니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 *lpDrawItemStruct* 함수 멤버 이전에 종료 합니다.  
  
 또한 참조는 [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) 스타일 값입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="getbitmap"></a>  CButton::GetBitmap  
 이 멤버 함수를 사용 하 여 이전에 설정 하는 비트맵의 핸들을 가져오려면 호출 [SetBitmap](#setbitmap), 즉 단추와 연결 된 합니다.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>반환 값  
 비트맵에 대 한 핸들입니다. **NULL** 비트맵이 없습니다 이전에 지정 하는 경우.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="getbuttonstyle"></a>  CButton::GetButtonStyle  
 단추 컨트롤의 스타일에 대 한 정보를 검색합니다.  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 대 한 단추 스타일 반환 `CButton` 개체입니다. 이 함수는만 반환 된 [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) 는 다른 창 스타일의 스타일 값입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="getcheck"></a>  CButton::GetCheck  
 라디오 단추 또는 확인란의 선택 상태를 검색합니다.  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 값 button 컨트롤을 사용 하 여 만든는 **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, 또는 **BS_3STATE** 스타일은 다음 값 중 하나:  
  
|값|의미|  
|-----------|-------------|  
|**BST_UNCHECKED**|단추 상태 선택 되지 않습니다.|  
|**BST_CHECKED**|단추 상태 검사 됩니다.|  
|**BST_INDETERMINATE**|단추의 상태는 확정적 (단추에 경우에 적용 되는 **BS_3STATE** 또는 **BS_AUTO3STATE** 스타일).|  
  
 반환 값은 단추에 다른 스타일을 **BST_UNCHECKED**합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="getcursor"></a>  CButton::GetCursor  
 이 멤버 함수를 사용 하 여 이전에 설정 된 커서의 핸들을 가져올 호출 [SetCursor](#setcursor), 즉 단추와 연결 된 합니다.  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>반환 값  
 커서 이미지에 대 한 핸들입니다. **NULL** 커서가 없습니다 이전에 지정 하는 경우.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="geticon"></a>  CButton::GetIcon  
 이 멤버 함수를 사용 하 여 이전에 설정 아이콘의 핸들을 가져오려면 호출 [SetIcon](#seticon), 즉 단추와 연결 된 합니다.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>반환 값  
 아이콘에 대 한 핸들입니다. **NULL** 아이콘이 없는 이전에 지정 하는 경우.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="getidealsize"></a>  CButton::GetIdealSize  
 단추 컨트롤에 대 한 이상적인 크기를 검색합니다.  
  
```  
BOOL GetIdealSize(SIZE* psize);
```  
  
### <a name="parameters"></a>매개 변수  
 *psize*  
 단추의 현재 크기에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 **BCM_GETIDEALSIZE** 메시지에 설명 된 대로 [단추](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK의 섹션입니다.  
  
##  <a name="getimagelist"></a>  CButton::GetImageList  
 단추 컨트롤에서 이미지 목록을 가져오려면이 메서드를 호출 합니다.  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbuttonImagelist*  
 이미지 목록에 대 한 포인터는 `CButton` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 **BCM_GETIMAGELIST** 메시지에 설명 된 대로 [단추](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK의 섹션입니다.  
  
##  <a name="getnote"></a>  CButton::GetNote  
 현재 명령 링크 컨트롤과 관련 된 메모 텍스트를 검색 합니다.  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] *lpszNote*|호출자가 할당 및 할당 취소에 대 한 버퍼에 대 한 포인터입니다. 반환 값이 `true`, 버퍼에 포함 되 고, 그렇지 않으면 현재 명령 링크 컨트롤에 연결 된 메모 텍스트, 버퍼는 변경 되지 않습니다.|  
|[out에서] *cchNote*|부호 없는 정수 변수에 대 한 포인터입니다.<br /><br /> 이 메서드를 호출할 때 변수에 의해 지정 된 버퍼의 크기를 포함 된 *lpszNote* 매개 변수입니다.<br /><br /> 이 메서드가 반환 될 때, 반환 값이 `true` 변수에 현재 명령 링크 컨트롤과 연결 된 참고의 크기를 포함 합니다. 반환 값이 `false`, 변수 메모를 포함 하는 데 필요한 버퍼 크기를 포함 합니다.|  
  
### <a name="return-value"></a>반환 값  
 첫 번째 오버 로드에서는 [CString](../../atl-mfc-shared/using-cstring.md) 현재 명령 링크 컨트롤과 관련 된 메모 텍스트를 포함 하는 개체입니다.  
  
 또는  
  
 두 번째 오버 로드에서 `true` 이 메서드가 성공적 이면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_COMMANDLINK` 또는 `BS_DEFCOMMANDLINK`합니다.  
  
 이 메서드는 전송 된 [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getnotelength"></a>  CButton::GetNoteLength  
 현재 명령 링크 컨트롤에 대 한 주석 텍스트의 길이 검색합니다.  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 명령 링크 컨트롤에 대 한 16 비트 유니코드 문자에 메모 텍스트의 길이입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_COMMANDLINK` 또는 `BS_DEFCOMMANDLINK`합니다.  
  
 이 메서드는 전송 된 [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getsplitglyph"></a>  CButton::GetSplitGlyph  
 현재는 분할 단추 컨트롤과 관련 된 문자를 검색 합니다.  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재는 분할 단추 컨트롤과 관련 된 문자 모양 문자입니다.  
  
### <a name="remarks"></a>설명  
 문자 모양을 특정 글꼴에 문자의 실제 표현입니다. 예를 들어 유니코드 확인 표시가 문자의 문자 모양으로 분할 단추 컨트롤을 데코레이팅 할 수 있습니다 (U + 2713).  
  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 이 메서드를 초기화는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체는 `BCSIF_GLYPH` 플래그 및 해당 구조에서 보냅니다는 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) 설명 하는 메시지 Windows SDK에서 이 메서드 검색 하 여 문자의 메시지 함수에서 반환 된 `himlGlyph` 구조체의 멤버입니다.  
  
##  <a name="getsplitimagelist"></a>  CButton::GetSplitImageList  
 검색 된 [이미지 목록을](../../mfc/reference/cimagelist-class.md) 현재 분할 단추 컨트롤에 대 한 합니다.  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 이 메서드를 초기화는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체는 `BCSIF_IMAGE` 플래그 및 해당 구조에서 보냅니다는 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) 설명 하는 메시지 Windows SDK에서 이 메서드는 이미지 목록에서 검색 메시지 함수에서 반환 된 `himlGlyph` 구조체의 멤버입니다.  
  
##  <a name="getsplitinfo"></a>  CButton::GetSplitInfo  
 Windows 현재 분할 단추 컨트롤을 만드는 방법을 결정 하는 매개 변수를 검색 합니다.  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] *pInfo*|에 대 한 포인터는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체 현재 분할 단추 컨트롤에 대 한 정보입니다. 호출자가 구조를 할당 해야 합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 이 메서드는 전송 된 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getsplitsize"></a>  CButton::GetSplitSize  
 현재는 분할 단추 컨트롤의 드롭다운 목록 구성 요소의 경계 사각형을 검색 합니다.  
  
```  
BOOL GetSplitSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] *pSize*|에 대 한 포인터는 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조체는 사각형의 설명입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 분할 단추 컨트롤을 확장 하 고, 목록 상자 또는 페이저 컨트롤 같은 드롭 다운 구성 요소를 표시할 수 있습니다. 이 메서드는 드롭 다운 구성 요소를 포함 하는 경계 사각형을 검색 합니다.  
  
 이 메서드를 초기화는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체는 `BCSIF_SIZE` 플래그 및 해당 구조에서 보냅니다는 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) 설명 하는 메시지 Windows SDK에서 이 메서드는 경계 사각형에서 검색 메시지 함수에서 반환 된 `size` 구조체의 멤버입니다.  
  
##  <a name="getsplitstyle"></a>  CButton::GetSplitStyle  
 현재 분할 단추 컨트롤을 정의 하는 분할 단추 스타일을 검색 합니다.  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 분할 단추 스타일의 비트 조합입니다. 자세한 내용은 참조는 `uSplitStyle` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 분할 단추 스타일 맞춤, 가로 세로 비율, 및 Windows는 분할 단추 아이콘을 그립니다 그래픽 형식 지정 합니다.  
  
 이 메서드를 초기화는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체는 `BCSIF_STYLE` 플래그 및 해당 구조에서 보냅니다는 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) 설명 하는 메시지 Windows SDK에서 이 메서드 검색에서 분할 단추 스타일 메시지 함수에서 반환 된 `uSplitStyle` 구조체의 멤버입니다.  
  
##  <a name="getstate"></a>  CButton::GetState  
 단추 컨트롤의 상태를 검색합니다.  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추 컨트롤의 현재 상태를 나타내는 값의 조합을 포함 하는 비트 필드입니다. 다음 표에서 가능한 값을 나열합니다.  
  
|단추 상태|값|설명|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|초기 상태입니다.|  
|`BST_CHECKED`|0x0001|단추 컨트롤이 선택 되어 있습니다.|  
|`BST_INDETERMINATE`|0x0002|비활성화 상태 (만 가능 단추 컨트롤에는 세 가지 상태에 있을 때)입니다.|  
|`BST_PUSHED`|0x0004|Button 컨트롤을 눌렀습니다.|  
|`BST_FOCUS`|0x0008|단추 컨트롤에 포커스가 있습니다.|  
  
### <a name="remarks"></a>설명  
 단추 컨트롤을는 `BS_3STATE` 또는 `BS_AUTO3STATE` 단추 스타일 비활성화 상태 라는 세 번째 상태에 있는 확인란을 만듭니다. 비활성화 상태 확인란 checked 또는 unchecked 아닙니다 임을 나타냅니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="gettextmargin"></a>  CButton::GetTextMargin  
 이 메서드를 호출의 텍스트 여백 가져오는 `CButton` 개체입니다.  
  
```  
BOOL GetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>매개 변수  
 *pmargin*  
 텍스트 여백에 대 한 포인터는 `CButton` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 텍스트 여백을 반환합니다.  
  
### <a name="remarks"></a>설명  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 **BCM_GETTEXTMARGIN** 메시지에 설명 된 대로 [단추](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK의 섹션입니다.  
  
##  <a name="setbitmap"></a>  CButton::SetBitmap  
 새 비트맵 단추와 연결 하려면이 함수를 호출 합니다.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 *hBitmap*  
 비트맵의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 단추와 연결 된 이전에 비트맵의 핸들입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 가운데에 정렬 하는 단추 비트맵을 자동으로 배치 됩니다. 비트맵 단추에 대해 너무 큰 경우 어느 한 쪽에 잘립니다. 다음을 포함 한 다른 맞춤 옵션을 선택할 수 있습니다.  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 와 달리 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), 단추, 당 4 개의 비트맵을 사용 하 여 `SetBitmap` 단추 당 하나의 비트맵을 사용 합니다. 단추를 누를 경우 비트맵 아래쪽 및 오른쪽 시프트 나타납니다.  
  
 비트맵을 마쳤을 때 해제 책임이 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="setbuttonstyle"></a>  CButton::SetButtonStyle  
 Button의 스타일을 변경합니다.  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *nStyle*  
 지정 된 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles)합니다.  
  
 *bRedraw*  
 그려야 하는 단추 인지 지정 합니다. 0이 아닌 값의 단추를 다시 그립니다. 0은 단추를 그려지지 않습니다. 단추는 기본적으로 다시 그려집니다.  
  
### <a name="remarks"></a>설명  
 사용 된 `GetButtonStyle` 멤버 함수를 단추 스타일을 검색 합니다. 완료 단추 스타일의 하위 단어는 단추 특정 스타일입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="setcheck"></a>  CButton::SetCheck  
 설정 하거나 라디오 단추 또는 확인란의 선택 상태를 다시 설정 합니다.  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>매개 변수  
 *nCheck*  
 선택 상태를 지정합니다. 이 매개 변수는 다음 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|**BST_UNCHECKED**|않음으로 단추 상태를 설정 합니다.|  
|**BST_CHECKED**|단추 상태 검사를 설정 합니다.|  
|**BST_INDETERMINATE**|단추 상태를 확인할 수 없는 설정. 단추에 경우에이 값을 사용할 수는 **BS_3STATE** 또는 **BS_AUTO3STATE** 스타일입니다.|  
  
### <a name="remarks"></a>설명  
 이 멤버 함수에 누름 영향을 주지 않습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="setcursor"></a>  CButton::SetCursor  
 새 커서를 단추와 연결 하려면이 함수를 호출 합니다.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>매개 변수  
 *hCursor*  
 커서의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 단추와 연결 된 커서의 핸들입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 가운데에 정렬 하는 단추 커서를 자동으로 배치 됩니다. 커서가 단추에 대해 너무 큰 경우 어느 한 쪽에 잘립니다. 다음을 포함 한 다른 맞춤 옵션을 선택할 수 있습니다.  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 와 달리 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), 단추, 당 4 개의 비트맵을 사용 하 여 `SetCursor` 단추 당 하나만 커서를 사용 합니다. 단추를 누를 때 아래쪽 및 오른쪽 시프트를 커서가 나타납니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="setdropdownstate"></a>  CButton::SetDropDownState  
 현재는 분할 단추 컨트롤의 드롭 다운 상태를 설정합니다.  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *fDropDown*|`true` 설정 하려면 `BST_DROPDOWNPUSHED` 상태가 `false`합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 분할 단추 컨트롤의 스타일에 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON` 고 단추 및 드롭다운 화살표는 권한 부여할 수를 구성 합니다. 자세한 내용은 참조 [단추 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775951)합니다. 일반적으로 드롭 다운 상태 드롭다운 화살표를 클릭할 때 설정 됩니다. 이 메서드를 사용 하 여 프로그래밍 방식으로 컨트롤의 드롭 다운 상태를 설정 합니다. 드롭다운 화살표 상태를 나타내는 음영 처리 된 그려집니다.  
  
 이 메서드는 전송 된 [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 *m_splitButton*즉, 분할 단추 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 드롭 다운 화살표 푸시 됨을 나타내기 위해 분할 단추 컨트롤의 상태를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="setelevationrequired"></a>  CButton::SetElevationRequired  
 현재 단추 컨트롤의 상태를 설정 `elevation required`는 높은 보안 아이콘을 표시 하려면 컨트롤에 대 한 데 필요 합니다.  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `fElevationRequired`|`true` 설정 하려면 `elevation required` 상태가 `false`합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 명령이 나 단추 링크 컨트롤 작업을 수행 하려면 관리자 권한 보안 권한이 필요한 경우 컨트롤을 설정 `elevation required` 상태입니다. 그 후 Windows 컨트롤에 사용자 계정 컨트롤 (UAC) 방패 아이콘을 표시합니다. 자세한 내용은에서 "사용자 계정 컨트롤" 참조 [MSDN](http://go.microsoft.com/fwlink/p/?linkid=18507)합니다.  
  
 이 메서드는 전송 된 [BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="seticon"></a>  CButton::SetIcon  
 새 아이콘 단추와 연결 하려면이 멤버 함수를 호출 합니다.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 *hIcon*  
 아이콘의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 단추와 연결 된 아이콘의 핸들입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 가운데에 정렬 하는 단추 아이콘을 자동으로 배치 됩니다. 아이콘 단추에 대해 너무 크면 어느 쪽에 잘립니다. 다음을 포함 한 다른 맞춤 옵션을 선택할 수 있습니다.  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 와 달리 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), 단추, 당 4 개의 비트맵을 사용 하 여 `SetIcon` 단추 당 하나의 아이콘을 사용 합니다. 단추를 누르면 아래쪽 및 오른쪽으로 이동 하는 아이콘이 나타납니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="setimagelist"></a>  CButton::SetImageList  
 이미지 목록을 설정 하려면이 메서드를 호출 하는 `CButton` 개체입니다.  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbuttonImagelist*  
 새 이미지 목록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 **BCM_SETIMAGELIST** 메시지에 설명 된 대로 [단추](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK의 섹션입니다.  
  
##  <a name="setnote"></a>  CButton::SetNote  
 현재 명령 링크 컨트롤에 대 한 메모 텍스트를 설정합니다.  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *lpszNote*|명령 링크 컨트롤에 대 한 메모 텍스트가로 설정 된 유니코드 문자열에 대 한 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_COMMANDLINK` 또는 `BS_DEFCOMMANDLINK`합니다.  
  
 이 메서드는 전송 된 [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 *m_cmdLink*, 즉 명령 링크 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 명령 링크 컨트롤에 대 한 메모 텍스트를 설정합니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="setsplitglyph"></a>  CButton::SetSplitGlyph  
 현재 분할 단추 컨트롤을 지정 된 문자 모양에 연결합니다.  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *chGlyph*|분할 단추 드롭다운 화살표도 사용할 문자를 지정 하는 문자입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일 있는 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 문자 모양을 특정 글꼴에 문자의 실제 표현입니다. *chGlyph* 매개 변수는 문자 모양으로 사용 되지 않지만 대신는 시스템에서 정의한 문자 집합에서 문자 모양을 선택 하는 데 사용 됩니다. 기본 드롭 다운 화살표 문자 모양을 '6' 문자로 지정 되 고 유니코드 문자 가리키는 아래로 검정색 삼각형 (U + 25BC)와 유사 합니다.  
  
 이 메서드를 초기화는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체는 `BCSIF_GLYPH` 플래그 및 `himlGlyph` 인 멤버는 `chGlyph` 매개 변수를 한 다음이 구조는 에서보냅니다[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK에 설명 된 메시지입니다.  
  
##  <a name="setsplitimagelist"></a>  CButton::SetSplitImageList  
 연결 프로그램 [이미지 목록을](../../mfc/reference/cimagelist-class.md) 현재 분할 단추 컨트롤을 사용 합니다.  
  
```  
BOOL SetSplitImageList(CImageList* pSplitImageList);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *pSplitImageList*|에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 현재 분할 단추 컨트롤에 할당 하는 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 이 메서드는 초기화는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체를 `BCSIF_IMAGE` 플래그 및 `himlGlyph` 인 멤버는 *pSplitImageList* 매개 변수를 한 다음 해당 구조 보냅니다는 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK에 설명 된 메시지입니다.  
  
##  <a name="setsplitinfo"></a>  CButton::SetSplitInfo  
 Windows 현재 분할 단추 컨트롤을 만드는 방법을 결정 하는 매개 변수를 지정 합니다.  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *pInfo*|에 대 한 포인터는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 현재 분할 단추 컨트롤을 정의 하는 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 이 메서드는 전송 된 [BCM_SETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775981) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 `m_splitButton`즉, 분할 단추 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 분할 단추 드롭다운 화살표에 사용 되는 문자 모양이 변경 됩니다. 이 예제에서는 기본 아래쪽 삼각형 문자에 대 한 위쪽 삼각형 문자를 대체합니다. 표시 되는 문자 모양에서 지정 하는 문자에 따라 달라 집니다는 `himlGlyph` 의 멤버는 `BUTTON_SPLITINFO` 구조입니다. 아래쪽 삼각형 문자 모양 지정 된 문자 ' 6' 및 위쪽을 가리키는 삼각형 문자 모양 문자 ' 5로 지정 된 '. 참조 편의 메서드를 비교 하기 위해 [CButton::SetSplitGlyph](#setsplitglyph)합니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
##  <a name="setsplitsize"></a>  CButton::SetSplitSize  
 현재는 분할 단추 컨트롤의 드롭다운 목록 구성 요소의 경계 사각형을 설정합니다.  
  
```  
BOOL SetSplitSize(LPSIZE pSize);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *pSize*|에 대 한 포인터는 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 경계 사각형을 설명 하는 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 분할 단추 컨트롤을 확장 하 고, 목록 상자 또는 페이저 컨트롤 같은 드롭 다운 구성 요소를 표시할 수 있습니다. 이 메서드는 드롭 다운 구성 요소를 포함 하는 경계 사각형의 크기를 지정 합니다.  
  
 이 메서드를 초기화 합니다는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체는 `BCSIF_SIZE` 플래그 및 `size` 인 멤버는 *pSize* 매개 변수를 하에 보냅니다 구조체는 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK에 설명 된 메시지입니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 `m_splitButton`즉, 분할 단추 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 분할 단추 드롭다운 화살표 크기 두 배로 만듭니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="setsplitstyle"></a>  CButton::SetSplitStyle  
 현재 분할 단추 컨트롤의 스타일을 설정 합니다.  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *uSplitStyle*|분할 단추 스타일의 비트 조합입니다. 자세한 내용은 참조는 `uSplitStyle` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 단추 스타일은 컨트롤에만 `BS_SPLITBUTTON` 또는 `BS_DEFSPLITBUTTON`합니다.  
  
 분할 단추 스타일 맞춤, 가로 세로 비율, 및 Windows는 분할 단추 아이콘을 그립니다 그래픽 형식 지정 합니다. 자세한 내용은 참조는 `uSplitStyle` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조입니다.  
  
 이 메서드를 초기화는 `mask` 의 멤버는 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) 구조체는 `BCSIF_STYLE` 플래그 및 `uSplitStyle` 인 멤버는 *uSplitStyle* 매개 변수를 한 다음 보냅니다 에 해당 구조는 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK에 설명 된 메시지입니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 `m_splitButton`즉, 분할 단추 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 분할 단추 드롭다운 화살표의 스타일을 설정 합니다. `BCSS_ALIGNLEFT` 단추의 왼쪽에 있는 화살표를 표시 하는 스타일 및 `BCSS_STRETCH` 스타일의 단추 크기를 조정할 때 드롭 다운 화살표의 비율을 유지 합니다.  
  
 [!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="setstate"></a>  CButton::SetState  
 Button 컨트롤을 강조 하는지 여부를 설정 합니다.  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>매개 변수  
 *bHighlight*  
 단추를 강조 표시 하는지 여부를 지정 합니다. 0이 아닌 값이 강조 표시 단추 변수를 모두 강조 표시를 제거합니다.  
  
### <a name="remarks"></a>설명  
 강조 표시 단추 컨트롤의 외부를 영향을 줍니다. 라디오 단추 또는 확인란의 선택 상태에 영향이 없습니다.  
  
 Button 컨트롤 사용자가을 마우스 왼쪽된 단추를 보유 하는 경우 자동으로 강조 표시 됩니다. 강조 표시를 사용자가 마우스 단추를 놓을 때 제거 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="settextmargin"></a>  CButton::SetTextMargin  
 텍스트 여백을 설정 하려면이 메서드를 호출 하는 `CButton` 개체입니다.  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>매개 변수  
 *pmargin*  
 새 텍스트 여백에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 **BCM_SETTEXTMARGIN** 메시지에 설명 된 대로 [단추](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK의 섹션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)   
 [CListBox 클래스](../../mfc/reference/clistbox-class.md)   
 [CScrollBar 클래스](../../mfc/reference/cscrollbar-class.md)   
 [CStatic 클래스](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton 클래스](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)
