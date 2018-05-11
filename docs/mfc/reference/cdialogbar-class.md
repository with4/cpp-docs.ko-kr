---
title: CDialogBar 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dbb2d8202e9b87d2825b7d40a0dde4323246aa0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdialogbar-class"></a>CDialogBar 클래스
컨트롤 막대에 Windows 모덜리스 대화 상자의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|`CDialogBar` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Windows 대화 상자 막대를 만들고 연결 하는 `CDialogBar` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 대화 상자 막대를 사용 하는 사용자 수 사이 이동 하는 표준 Windows 컨트롤을 포함 하는 대화 상자가 유사 합니다. 다른 유사성은 대화 상자 막대를 나타내기 위해 대화 상자 템플릿을 만들어야 합니다.  
  
 만들기 및 대화 상자 막대를 사용 하 여 만들기 및 사용 하는 것과 비슷합니다는 `CFormView` 개체입니다. 먼저, 사용 하 여는 [대화 상자 편집기](../../windows/dialog-editor.md) 스타일으로 대화 상자 템플릿을 정의 하 **WS_CHILD** 및 다른 스타일이 없습니다. 서식 파일에는 스타일 없어야 합니다. **WS_VISIBLE**합니다. 응용 프로그램 코드에서 호출을 만드는 생성자는 `CDialogBar` 개체를 호출 하십시오 **만들기** 대화 상자 막대 창을 만들고에 연결 하는 `CDialogBar` 개체입니다.  
  
 대 한 자세한 내용은 `CDialogBar`, 문서를 참조 [대화 상자 모음](../../mfc/dialog-bars.md) 및 [Technical Note 31](../../mfc/tn031-control-bars.md), 컨트롤 막대입니다.  
  
> [!NOTE]
>  현재 릴리스에서 `CDialogBar` 개체는 Windows Forms 컨트롤을 호스트할 수 없습니다. Visual c + +에서 Windows Forms 컨트롤에 대 한 자세한 내용은 참조 [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar  
 `CDialogBar` 개체를 생성합니다.  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>  CDialogBar::Create  
 지정 된 대화 상자 리소스 템플릿을 로드 `lpszTemplateName` 또는 `nIDTemplate`, 대화 상자 막대 창을 만듭니다의 스타일을 설정 하 고 사용 하 여 연결 된 `CDialogBar` 개체입니다.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
virtual BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentWnd`  
 부모에 대 한 포인터 `CWnd` 개체입니다.  
  
 `lpszTemplateName`  
 이름에 대 한 포인터는 `CDialogBar` 개체의 대화 상자 리소스 템플릿.  
  
 `nStyle`  
 도구 모음 스타일입니다. 지원 되는 추가 도구 모음 스타일은  
  
- `CBRS_TOP` 컨트롤 막대 프레임 창의 위쪽에입니다.  
  
- `CBRS_BOTTOM` 컨트롤 막대 프레임 창 맨 아래에입니다.  
  
- `CBRS_NOALIGN` 부모 크기를 조정할 때 컨트롤 막대 위치가 변경 되지 않습니다.  
  
- `CBRS_TOOLTIPS` 컨트롤 막대에는 도구 설명을 표시합니다.  
  
- **CBRS_SIZE_DYNAMIC** 동적 컨트롤 막대입니다.  
  
- **CBRS_SIZE_FIXED** 컨트롤 막대 고정 됩니다.  
  
- **CBRS_FLOATING** 컨트롤 막대 부동 합니다.  
  
- `CBRS_FLYBY` 상태 표시줄 단추에 대 한 정보를 표시합니다.  
  
- **CBRS_HIDE_INPLACE** 컨트롤 막대 사용자에 게 표시 되지 않습니다.  
  
 `nID`  
 대화 상자 막대의 컨트롤 ID입니다.  
  
 `nIDTemplate`  
 리소스 ID는 `CDialogBar` 개체의 대화 상자 템플릿.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 하는 경우는 `CBRS_TOP` 또는 `CBRS_BOTTOM` 맞춤 스타일 대화 상자 막대 너비 프레임 창의 방식과 높이가 이므로로 지정 된 리소스의 `nIDTemplate`합니다. 지정 하는 경우는 `CBRS_LEFT` 또는 `CBRS_RIGHT` 맞춤 스타일 대화 상자 막대의 높이 프레임 창 이며 너비 지정 하는 리소스의 `nIDTemplate`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFormView 클래스](../../mfc/reference/cformview-class.md)   
 [CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)
