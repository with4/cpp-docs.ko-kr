---
title: CCmdUI 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
dev_langs:
- C++
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf80f2ebea8fe27596ce1b240cc414cc0db7a8db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ccmdui-class"></a>CCmdUI 클래스
내 에서만 사용 되는 `ON_UPDATE_COMMAND_UI` 의 처리기는 `CCmdTarget`-클래스를 파생 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|현재 메시지 처리기의 체인을 라우팅 계속 하려면는 명령 라우팅 메커니즘을 알려줍니다.|  
|[CCmdUI::Enable](#enable)|이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CCmdUI::SetCheck](#setcheck)|이 명령에 대 한 사용자 인터페이스 항목의 선택 상태를 설정합니다.|  
|[CCmdUI::SetRadio](#setradio)|마찬가지로 `SetCheck` 멤버 함수는 하지만 라디오 그룹에 작동 합니다.|  
|[CCmdUI::SetText](#settext)|이 명령에 대 한 사용자 인터페이스 항목에 대 한 텍스트를 설정합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|사용자 인터페이스 개체의 ID입니다.|  
|[CCmdUI::m_nIndex](#m_nindex)|사용자 인터페이스 개체의 인덱스입니다.|  
|[CCmdUI::m_pMenu](#m_pmenu)|가 나타내는 메뉴 가리키는 `CCmdUI` 개체입니다.|  
|[CCmdUI::m_pOther](#m_pother)|알림을 보낸 window 개체를 가리킵니다.|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|가 나타내는 포함 된 하위 메뉴를 가리키는 `CCmdUI` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CCmdUI` 기본 클래스는 없습니다.  
  
 때 응용 프로그램의 사용자 메뉴, 각 메뉴 항목 알아야 것을 표시 해야 하는지를 사용 또는 사용 안 함 아래로 끌어옵니다. 구현 하 여이 정보를 제공 하는 메뉴 명령 대상일은 `ON_UPDATE_COMMAND_UI` 처리기입니다. 각 응용 프로그램의 명령 사용자 인터페이스 개체에 대 한 각 처리기에 대 한 메시지 맵 항목 및 함수 프로토타입을 만드는 속성 창을 사용 합니다.  
  
 메뉴 끌어온, 하는 경우 프레임 워크에 대 한 검색 하 고 각각 호출 `ON_UPDATE_COMMAND_UI` 처리기, 각 처리기를 호출 `CCmdUI` 멤버와 같은 함수가 **사용** 및 **확인**, 및 다음 프레임 워크 각 메뉴 항목을 적절 하 게 표시합니다.  
  
 메뉴 항목을 바꿀 수 있습니다는 컨트롤 막대 단추 또는 다른 명령 사용자 인터페이스 개체 내의 코드를 변경 하지 않고는 `ON_UPDATE_COMMAND_UI` 처리기입니다.  
  
 다음 표에서 요약 효과 `CCmdUI`의 다양 한 명령 사용자 인터페이스 항목에 있는 멤버 함수입니다.  
  
|사용자 인터페이스 항목|사용|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|Menu item|사용 가능 / 불가능|선택 하거나 선택 취소|점을 사용 하 여 검사|집합 텍스트 항목|  
|도구 모음 단추|사용 가능 / 불가능|선택 하는,을 선택 취소 또는 결정 되지 않은|`SetCheck`과 같음|(해당 없음)|  
|상태 표시줄 창|텍스트를 표시 하거나 숨길 만듭니다.|집합 팝아웃 또는 일반 테두리|`SetCheck`과 같음|창 텍스트를 설정합니다.|  
|일반 단추 `CDialogBar`|사용 가능 / 불가능|확인란을 선택 하거나 선택 취소|`SetCheck`과 같음|단추 텍스트 설정|  
|일반적인 제어 `CDialogBar`|사용 가능 / 불가능|(해당 없음)|(해당 없음)|창 텍스트를 설정합니다.|  
  
 이 클래스의 사용에 관한 자세한 내용은 [사용자 인터페이스 개체 업데이트 하는 방법을](../../mfc/how-to-update-user-interface-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CCmdUI`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="continuerouting"></a>  CCmdUI::ContinueRouting  
 명령 라우팅 메커니즘의 처리기 체인에서 현재 메시지를 라우팅하기 계속 하 게이 멤버 함수를 호출 합니다.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>설명  
 와 함께에서 사용 해야 하는 고급 멤버 함수는 `ON_COMMAND_EX` 반환 하는 처리기 **FALSE**합니다. 자세한 내용은 참조 [기술 참고 6](../../mfc/tn006-message-maps.md)합니다.  
  
##  <a name="enable"></a>  CCmdUI::Enable  
 이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 하거나 설정 하려면이 함수를 호출 합니다.  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bOn`  
 **True 이면** 해당 항목을 사용할 수 있도록 **FALSE** 사용 하지 않도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="m_nid"></a>  CCmdUI::m_nID  
 메뉴 항목, 도구 모음 단추 또는가 나타내는 다른 사용자 인터페이스 개체의 ID는 `CCmdUI` 개체입니다.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_nindex"></a>  CCmdUI::m_nIndex  
 메뉴 항목, 도구 모음 단추 또는가 나타내는 다른 사용자 인터페이스 개체의 인덱스는 `CCmdUI` 개체입니다.  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="m_pmenu"></a>  CCmdUI::m_pMenu  
 포인터 (의 `CMenu` 형식)으로 표시 되는 메뉴에는 `CCmdUI` 개체입니다.  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>설명  
 **NULL** 경우 메뉴 항목이 아닙니다.  
  
##  <a name="m_psubmenu"></a>  CCmdUI::m_pSubMenu  
 포인터 (의 `CMenu` 형식)으로 표시 되는 포함 된 하위 메뉴에는 `CCmdUI` 개체입니다.  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>설명  
 **NULL** 경우 메뉴 항목이 아닙니다. 하위 메뉴 팝업 경우 `m_nID` 팝업 메뉴의 첫 번째 항목의 ID를 포함 합니다. 자세한 내용은 참조 [기술 참고 21](../../mfc/tn021-command-and-message-routing.md)합니다.  
  
##  <a name="m_pother"></a>  CCmdUI::m_pOther  
 포인터 (형식의 `CWnd`) 알림을 전송 하는 도구 또는 상태 표시줄 등의 창 개체입니다.  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>설명  
 **NULL** 항목이 메뉴 또는 비-인지 `CWnd` 개체입니다.  
  
##  <a name="setcheck"></a>  CCmdUI::SetCheck  
 이 명령에 대 한 사용자 인터페이스 항목 적절 한 선택 상태를 설정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCheck`  
 설정 하려면 선택 상태를 지정 합니다. 0을 선택 하거나 선택 하지 않으면 하는 경우 1, 검사 하는 경우 2 인 경우, 비활성화 상태를 가져오거나 설정 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 메뉴 항목 및 도구 모음 단추에 대 한 작동합니다. 비활성화 상태 도구 모음 단추에만 적용 됩니다.  
  
##  <a name="setradio"></a>  CCmdUI::SetRadio  
 이 명령에 대 한 사용자 인터페이스 항목 적절 한 선택 상태를 설정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bOn`  
 **True 이면** ; 항목을 설정 하려면 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 같은 있는데 `SetCheck`라디오 그룹의 일부로 작동 하는 사용자 인터페이스 항목에 작동 한다는 점을 제외 하면, 합니다. 그룹에 다른 항목을 선택 취소 하면 자체 라디오 그룹 동작을 유지 하지 않는 한 자동 되지 않습니다.  
  
##  <a name="settext"></a>  CCmdUI::SetText  
 이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 텍스트 문자열에 대 한 포인터입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MDI MFC 샘플](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
