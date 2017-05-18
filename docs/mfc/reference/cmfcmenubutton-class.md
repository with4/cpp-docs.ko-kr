---
title: "CMFCMenuButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton class
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 65c334ce68dbbbae2b21da2c40aa9420cdeb51bd
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton 클래스
사용자가 선택한 메뉴에 팝업 메뉴와 보고서를 표시하는 단추입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|`CMFCMenuButton` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|디스패치 되기 전에 창 메시지를 변환 하는 프레임 워크에서 호출 됩니다. (`CMFCButton::PreTranslateMessage`를 재정의합니다.)|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|텍스트 및 이미지 크기에 따라 단추 크기를 변경합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|기본 시스템 팝업 메뉴를 표시 하거나 사용 하려면 여부를 지정 [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)합니다.|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|팝업 메뉴 또는 단추 오른쪽 아래에 있는 나타날지 여부를 지정 합니다.|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|단추를 놓을 후 메뉴 단추 상태를 변경 하는지 여부를 지정 합니다.|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|연결 된 창 메뉴에 대 한 핸들입니다.|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|어떤 항목을 나타내는 식별자 사용자가 팝업 메뉴에서 선택 합니다.|  
  
## <a name="remarks"></a>주의  
 `CMFCMenuButton` 에서 파생 된 클래스는 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md) , 차례로에서 파생 된는 [CButton 클래스](../../mfc/reference/cbutton-class.md)합니다. 따라서 사용할 수 있습니다 `CMFCMenuButton` 사용 같은 방식으로 코드에서 `CButton`합니다.  
  
 만들 때 한 `CMFCMenuButton`, 연결 된 팝업 메뉴에 대 한 핸들을 전달 해야 합니다. 그런 다음 함수를 호출 `CMFCMenuButton::SizeToContent`합니다. `CMFCMenuButton::SizeToContent`단추 크기는 팝업 창이 나타날 위치-즉, 아래 또는 단추 오른쪽을 가리키는 화살표를 포함 하는 데 충분 한지 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 단추에 첨부 하는 메뉴의 핸들을 설정 하 고 해당 텍스트와 이미지 크기에 따라 단추 크기를 조정 프레임 워크에 의해 표시 되는 팝업 메뉴를 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls #&38;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&39;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmenubutton.h  
  
##  <a name="cmfcmenubutton"></a>CMFCMenuButton::CMFCMenuButton  
 새 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) 개체입니다.  
  
```  
CMFCMenuButton();
```  
  
##  <a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu  
 팝업 메뉴를 나타내는 부울 멤버 변수는 프레임 워크를 표시 합니다.  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>주의  
 경우 `m_bOSMenu` 는 `TRUE`, 프레임 워크 호출의 상속 된 `TrackPopupMenu` 이 개체에 대 한 메서드. 그렇지 않으면 프레임 워크 호출 [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)합니다.  
  
##  <a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow  
 팝업 메뉴의 위치를 나타내는 부울 멤버 변수입니다.  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>주의  
 사용자가 메뉴 단추를 누르면 응용 프로그램이 팝업 메뉴에 표시 됩니다. 프레임 워크 단추 아래 또는 단추 오른쪽에 팝업 메뉴에 표시 됩니다. 이 단추는 팝업 메뉴가 표시 되는 위치를 나타내는 작은 화살표를 있습니다. 경우 `m_bRightArrow` 는 `TRUE`, 프레임 워크가 단추의 오른쪽에 팝업 메뉴를 표시 합니다. 그렇지 않은 경우 단추 아래에 있는 팝업 메뉴를 표시합니다.  
  
##  <a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed  
 사용자가 팝업 메뉴에서 항목을 선택 하는 동안 메뉴 단추가 표시 되는지를 나타내는 부울 멤버 변수를 눌렀습니다.  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>주의  
 하는 경우는 `m_bStayPressed` 멤버는 `FALSE`, 메뉴 단추 않습니다 될 누르지 때 사용 하는 단추를 클릭 합니다. 이 경우에 프레임 워크만 팝업 메뉴를 표시합니다.  
  
 하는 경우는 `m_bStayPressed` 멤버는 `TRUE`, 단추를 클릭할 때 메뉴 단추 누름 됩니다. 사용자 선택 하거나 취소 하 여 팝업 메뉴를 닫은 후 될 때까지 누른 유지 합니다.  
  
##  <a name="m_hmenu"></a>CMFCMenuButton::m_hMenu  
 연결 된 메뉴에 대 한 핸들입니다.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>주의  
 프레임 워크 메뉴 단추를 클릭할 때이 멤버 변수에서 표시 된 메뉴를 표시 합니다.  
  
##  <a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult  
 어떤 항목을 나타내는 정수 사용자가 팝업 메뉴에서 선택 합니다.  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>주의  
 사용자가 메뉴를 선택 하지 않고 취소 또는 오류가 발생 하는 경우이 멤버 변수의 값은&0;입니다.  
  
##  <a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage  
 디스패치 되기 전에 창 메시지를 변환 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMsg`  
 가리키는 [MSG](../../mfc/reference/msg-structure1.md) 처리할 메시지를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지 변환 되었습니다 발송 되어야 합니다; 경우에 0이 아닌 메시지 변환 되지 되었습니다 및 디스패치해야 하는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="sizetocontent"></a>CMFCMenuButton::SizeToContent  
 텍스트 크기와 이미지 크기에 따라 단추 크기를 변경합니다.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bCalcOnly`  
 이 메서드는 단추 크기가 조정 되는지를 나타내는 부울 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 단추에 대 한 새 크기를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는 경우 및 `bCalcOnly` 는 `TRUE`, `SizeToContent` 버튼의 새 크기에만 계산 됩니다.  
  
 버튼의 새 크기에 맞게 단추 텍스트, 이미지 및 화살표 계산 됩니다. 프레임 워크는 또한 가로 가장자리에 대 한 10 픽셀 및 5 픽셀 수직 가장자리에 대 한 미리 정의 된 여백에 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md)

