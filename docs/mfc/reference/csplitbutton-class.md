---
title: "CSplitButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
dev_langs:
- C++
helpviewer_keywords:
- CSplitButton class
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: 24
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
ms.openlocfilehash: b4c038a177d5c501d4baad8eaa208af0e76ce231
ms.lasthandoff: 02/24/2017

---
# <a name="csplitbutton-class"></a>CSplitButton 클래스
`CSplitButton` 클래스 분할 단추 컨트롤을 나타냅니다. 분할 단추 컨트롤은 사용자가 단추의 주요 부분을 클릭할 때 기본 동작을 수행하고 사용자가 단추의 드롭다운 화살표를 클릭하면 드롭다운 메뉴를 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|`CSplitButton` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|지정 된 스타일으로 분할 단추 컨트롤을 만들고 현재 연결 `CSplitButton` 개체입니다.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|현재는 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시 되는 드롭다운 메뉴를 설정 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|처리는 `BCN_DROPDOWN` 는 현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭 하면 시스템에서 보내는 알림입니다.|  
  
## <a name="remarks"></a>주의  
 `CSplitButton` 에서 파생 된 클래스는 [CButton](../../mfc/reference/cbutton-class.md) 클래스입니다. 분할 단추 컨트롤 하는 단추 컨트롤 스타일 `BS_SPLITBUTTON`합니다. 사용자가 드롭다운 화살표를 클릭 하면 사용자 지정 메뉴를 표시 합니다. 자세한 내용은 참조는 `BS_SPLITBUTTON` 및 `BS_DEFSPLITBUTTON` 스타일을 [단추 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775951)합니다.  
  
 다음 그림은 pager 컨트롤 및 (1) 분할 단추 컨트롤을 포함 하는 대화 상자를 보여 줍니다. (2) 드롭다운 화살표를 이미 클릭 하 고 (3) 하위 메뉴가 표시 됩니다.  
  
 ![Splitbutton 및 pager 컨트롤이 있는 대화 상자입니다. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
 이 클래스에서 지원 됩니다 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 이상.  
  
 이 클래스에 대 한 추가 요구 사항에 설명 되어 [빌드 요구 사항에 대 한 Windows Vista 공용 컨트롤](../../mfc/build-requirements-for-windows-vista-common-controls.md)합니다.  
  
##  <a name="create"></a>CSplitButton::Create  
 지정 된 스타일으로 분할 단추 컨트롤을 만들고 현재 연결 `CSplitButton` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `dwStyle`|컨트롤에 적용 될 스타일의 비트 조합 (OR)입니다. 자세한 내용은 참조 [단추 스타일](../../mfc/reference/button-styles.md)합니다.|  
|[in] `rect`|에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|  
|[in] `pParentWnd`|에 대 한 null이 아닌 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다.|  
|[in] `nID`|컨트롤의 ID입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="csplitbutton"></a>CSplitButton::CSplitButton  
 `CSplitButton` 개체를 생성합니다. 생성자의 매개 변수는 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시 되는 하위 메뉴를 지정 합니다.  
  
```  
CSplitButton();

 
CSplitButton(
    UINT nMenuId,   
    UINT nSubMenuId)  
CSplitButton(CMenu* pMenu)  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `nMenuId`|메뉴 표시줄의 리소스 ID입니다.|  
|[in] `nSubMenuId`|하위 메뉴의 리소스 ID입니다.|  
|[in] `pMenu`|에 대 한 포인터는 [CMenu](../../mfc/reference/cmenu-class.md) 하위 메뉴를 지정 하는 개체입니다. `CSplitButton` 개체 삭제는 `CMenu` 개체와 연결 된 `HMENU` 때는 `CSplitButton` 개체가 범위를 벗어난 있습니다.|  
  
### <a name="remarks"></a>주의  
 사용 된 [CSplitButton::Create](#create) 분할 단추 컨트롤을 만들고에 연결 하는 메서드는 `CSplitButton` 개체입니다.  
  
##  <a name="ondropdown"></a>CSplitButton::OnDropDown  
 처리는 `BCN_DROPDOWN` 는 현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭 하면 시스템에서 보내는 알림입니다.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pNMHDR`|에 대 한 포인터는 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) 구조에 대 한 정보를 포함 하는 [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) 알림.|  
|[out] `pResult`|(사용 되지 않습니다) 아무 값도 반환 합니다. 반환 값은 [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) 알림.|  
  
### <a name="remarks"></a>주의  
 사용자가 분할 단추 컨트롤에 있는 드롭다운 화살표를 클릭 하면 시스템 보냅니다는 `BCN_DROPDOWN` 알림 메시지는 `OnDropDown` 메서드 핸들입니다. 그러나는 `CSplitButton` 개체를 전달 하지 않습니다는 `BCN_DROPDOWN` 분할 단추 컨트롤을 포함 하는 컨트롤에는 알림입니다. 따라서 포함 하는 컨트롤 알림에 대 한 응답으로 사용자 지정 작업을 지원할 수 없습니다.  
  
 포함 하는 컨트롤을 지원 하는 사용자 지정 동작을 구현 하려면 사용을 [CButton](../../mfc/reference/cbutton-class.md) 개체의 스타일으로 `BS_SPLITBUTTON` 대신는 `CSplitButton` 개체입니다. 그런 다음에 대 한 처리기를 구현에서 `BCN_DROPDOWN` 에서 알림을 `CButton` 개체입니다. 자세한 내용은 참조 [단추 스타일](../../mfc/reference/button-styles.md)합니다.  
  
 분할 단추를 제어 하는 자체 지원 하 여 사용자 지정 동작을 구현 하려면 사용 [리플렉션 메시지](../../mfc/tn062-message-reflection-for-windows-controls.md)합니다. 고유한 클래스를 파생 되는 `CSplitButton` 클래스 및 이름을, 예를 들어 CMySplitButton 합니다. 그런 다음 다음과 같은 메시지 맵을 응용 프로그램에 추가 처리 하는 `BCN_DROPDOWN` 알림:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>CSplitButton::SetDropDownMenu  
 현재는 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시 되는 드롭다운 메뉴를 설정 합니다.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `nMenuId`|메뉴 표시줄의 리소스 ID입니다.|  
|[in] `nSubMenuId`|하위 메뉴의 리소스 ID입니다.|  
|[in] `pMenu`|에 대 한 포인터는 [CMenu](../../mfc/reference/cmenu-class.md) 하위 메뉴를 지정 하는 개체입니다. `CSplitButton` 개체 삭제는 `CMenu` 개체와 연결 된 `HMENU` 때는 `CSplitButton` 개체가 범위를 벗어난 있습니다.|  
  
### <a name="remarks"></a>주의  
 `nMenuId` 매개 변수는 메뉴 모음 항목의 가로 목록 메뉴 표시줄을 식별 합니다. `nSubMenuId` 매개 변수는는 드롭다운 목록에서 메뉴 항목에 연결 된 각 메뉴 모음 항목의 하위 메뉴를 식별 하는 인덱스 번호는&0;부터 시작 합니다. 예를 들어 일반적인 응용 프로그램에 포함 하는 메뉴가 메뉴 모음 항목을 "File" "편집" 및 "Help"입니다. "File" 메뉴 모음 항목에 하위 메뉴가 메뉴 항목이 포함 된 "Open," "닫기" 및 "종료"입니다. 분할 단추 컨트롤의 드롭다운 화살표를 클릭 하면 지정 된 하위 메뉴의 메뉴 모음 하지 컨트롤에 표시 됩니다.  
  
 다음 그림은 pager 컨트롤 및 (1) 분할 단추 컨트롤을 포함 하는 대화 상자를 보여 줍니다. (2) 드롭다운 화살표를 이미 클릭 하 고 (3) 하위 메뉴가 표시 됩니다.  
  
 ![Splitbutton 및 pager 컨트롤이 있는 대화 상자입니다. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>예제  
 다음 코드 예제에서 첫 번째 문을 보여 줍니다는 [CSplitButton::SetDropDownMenu](#setdropdownmenu) 메서드. 만든 메뉴는 Visual studio 메뉴 모음 ID 이름이 자동으로 지정 하는 리소스 편집기 `IDR_MENU1`합니다. `nSubMenuId` 매개 변수를&0; 인 메뉴 표시줄의 유일한 하위 메뉴를 가리킵니다.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;&1;](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CSplitButton 클래스](../../mfc/reference/csplitbutton-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CButton 클래스](../../mfc/reference/cbutton-class.md)

