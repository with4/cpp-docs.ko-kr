---
title: "CCmdUI 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, updating
- states, updating user interface object
- updating user interfaces for commands
- commands [C++], updating UI
- CCmdUI class
- toolbars [C++], updating
- command user interface
- menus [C++], updating as context changes
- buttons [C++], updating as context changes
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: 21
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: beb84a0f0f96c7a8acb5c432c7402b3e62b94518
ms.lasthandoff: 02/24/2017

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
|[CCmdUI::ContinueRouting](#continuerouting)|현재 메시지의 처리기는 체인을 계속 하려면 명령 라우팅 메커니즘에 알려줍니다.|  
|[CCmdUI::Enable](#enable)|이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CCmdUI::SetCheck](#setcheck)|이 명령에 대 한 사용자 인터페이스 항목의 선택 상태를 설정합니다.|  
|[CCmdUI::SetRadio](#setradio)|마찬가지로 `SetCheck` 멤버 함수는 하지만 라디오 그룹에 작동 합니다.|  
|[CCmdUI::SetText](#settext)|이 명령에 대 한 사용자 인터페이스 항목에 대 한 텍스트를 설정합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|사용자 인터페이스 개체의 ID입니다.|  
|[CCmdUI::m_nIndex](#m_nindex)|사용자 인터페이스 개체의 인덱스입니다.|  
|[CCmdUI::m_pMenu](#m_pmenu)|으로 표시 되는 메뉴를 가리키는 `CCmdUI` 개체입니다.|  
|[CCmdUI::m_pOther](#m_pother)|알림을 전송 하는 창 개체를 가리킵니다.|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|가 나타내는 포함 된 하위 메뉴를 가리키는 `CCmdUI` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `CCmdUI`기본 클래스는 없습니다.  
  
 때 응용 프로그램의 사용자는 메뉴, 각 메뉴 항목 알아야 표시할지 여부를 것으로 사용 하도록 설정 또는 사용 안 함으로 아래로 끌어옵니다. 구현 하 여이 정보를 제공 하는 메뉴 명령 대상일은 `ON_UPDATE_COMMAND_UI` 처리기입니다. 각 응용 프로그램의 명령 사용자 인터페이스 개체에 대 한 각 처리기에 대 한 메시지 맵 항목 및 함수 프로토타입을 만드는 속성 창을 사용 합니다.  
  
 메뉴를 끌어올는, 하는 경우 프레임 워크에 대 한 검색 하 고 각 호출 `ON_UPDATE_COMMAND_UI` 처리기, 각 처리기를 호출 `CCmdUI` 멤버와 같은 함수가 **사용** 및 **확인**, 프레임 워크 다음 적절 하 게 각 메뉴 항목을 표시 합니다.  
  
 메뉴 항목 내에서 코드를 변경 하지 않고 컨트롤 막대 단추 또는 다른 명령 사용자 인터페이스 개체를 대체할 수 있습니다는 `ON_UPDATE_COMMAND_UI` 처리기입니다.  
  
 다음 표에서 효과 요약 `CCmdUI`의 다양 한 명령 사용자 인터페이스 항목에 있는 멤버 함수입니다.  
  
|사용자 인터페이스 항목|사용|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|Menu item|사용 하도록 설정 하거나 해제 합니다.|선택 하거나 선택 취소 (×)|점 (•)를 사용 하 여 검사|집합 항목 텍스트|  
|도구 모음 단추|사용 하도록 설정 하거나 해제 합니다.|선택, 취소, 또는 결정 되지 않은|와 동일`SetCheck`|(해당 사항 없음)|  
|상태 표시줄 창|텍스트가 표시 되거나 숨겨지도록|집합 팝아웃 또는 일반 테두리|와 동일`SetCheck`|창 텍스트를 설정합니다.|  
|표준 단추`CDialogBar`|사용 하도록 설정 하거나 해제 합니다.|확인란을 선택 하거나 선택 취소|와 동일`SetCheck`|단추 텍스트 설정|  
|일반적인 제어`CDialogBar`|사용 하도록 설정 하거나 해제 합니다.|(해당 사항 없음)|(해당 사항 없음)|창 텍스트를 설정합니다.|  
  
 이 클래스의 사용에 관한 자세한 내용은 [사용자 인터페이스 개체 업데이트 하는 방법을](../../mfc/how-to-update-user-interface-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CCmdUI`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namecontinueroutinga--ccmduicontinuerouting"></a><a name="continuerouting"></a>CCmdUI::ContinueRouting  
 현재 메시지의 처리기는 체인을 계속 하려면 명령 라우팅 메커니즘을 지시 하려면이 멤버 함수를 호출 합니다.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>주의  
 와 함께에서 사용 해야 하는 고급 멤버 함수는 `ON_COMMAND_EX` 반환 하는 처리기 **FALSE**합니다. 자세한 내용은 참조 [기술 참고 6](../../mfc/tn006-message-maps.md)합니다.  
  
##  <a name="a-nameenablea--ccmduienable"></a><a name="enable"></a>CCmdUI::Enable  
 이 명령에 대 한 사용자 인터페이스 항목을 사용할지 여부를이 멤버 함수를 호출 합니다.  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bOn`  
 **True 이면** 해당 항목을 사용할 수 있도록 **FALSE** 사용 하지 않도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&46;](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&47;](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="a-namemnida--ccmduimnid"></a><a name="m_nid"></a>CCmdUI::m_nID  
 메뉴 항목, 도구 모음 단추 또는 나타내는 기타 사용자 인터페이스 개체의 ID는 `CCmdUI` 개체입니다.  
  
```  
UINT m_nID;  
```  
  
##  <a name="a-namemnindexa--ccmduimnindex"></a><a name="m_nindex"></a>CCmdUI::m_nIndex  
 메뉴 항목, 도구 모음 단추 또는 나타내는 기타 사용자 인터페이스 개체의 인덱스는 `CCmdUI` 개체입니다.  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="a-namempmenua--ccmduimpmenu"></a><a name="m_pmenu"></a>CCmdUI::m_pMenu  
 포인터 (의 `CMenu` 형식)으로 표시 되는 메뉴에는 `CCmdUI` 개체입니다.  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>주의  
 **NULL** 메뉴 항목이 경우.  
  
##  <a name="a-namempsubmenua--ccmduimpsubmenu"></a><a name="m_psubmenu"></a>CCmdUI::m_pSubMenu  
 포인터 (의 `CMenu` 형식)를 나타내는 포함 된 하위 메뉴는 `CCmdUI` 개체입니다.  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>주의  
 **NULL** 메뉴 항목이 경우. 하위 메뉴에 팝업 경우 `m_nID` 팝업 메뉴의 첫 번째 항목의 ID를 포함 합니다. 자세한 내용은 참조 [기술 참고 21](../../mfc/tn021-command-and-message-routing.md)합니다.  
  
##  <a name="a-namempothera--ccmduimpother"></a><a name="m_pother"></a>CCmdUI::m_pOther  
 포인터 (형식의 `CWnd`) 알림을 전송 하는 상태 또는 도구 모음과 같이 창 개체에 있습니다.  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>주의  
 **NULL** 항목이 메뉴 또는 비-인지 `CWnd` 개체입니다.  
  
##  <a name="a-namesetchecka--ccmduisetcheck"></a><a name="setcheck"></a>CCmdUI::SetCheck  
 이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCheck`  
 설정 하려면 선택 상태를 지정 합니다. 경우 0을 선택 하거나 선택 취소 합니다. 1, 검사 합니다. 2 인 경우, 비활성화 상태를 가져오거나 설정 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 메뉴 항목 및 도구 모음 단추에 대해 작동합니다. 비활성화 상태 도구 모음 단추에만 적용 됩니다.  
  
##  <a name="a-namesetradioa--ccmduisetradio"></a><a name="setradio"></a>CCmdUI::SetRadio  
 이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bOn`  
 **True 이면** ; 항목을 사용 하도록 설정 하려면 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수 작동 방식이 `SetCheck`점을 제외 하 고 사용자 인터페이스 항목 라디오 그룹의 일부로 역할에서 작동 합니다. 그룹의 다른 항목의 선택을 취소 하지 않으면 자동 자체 라디오 그룹 동작을 유지 합니다.  
  
##  <a name="a-namesettexta--ccmduisettext"></a><a name="settext"></a>CCmdUI::SetText  
 이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 텍스트 문자열에 대 한 포인터입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&48;](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDI](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)

