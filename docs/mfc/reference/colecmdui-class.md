---
title: "COleCmdUI 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- document object server
- COleCmdUI class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
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
ms.openlocfilehash: 38e7019d7636166262028d955455cee675824f8b
ms.lasthandoff: 02/24/2017

---
# <a name="colecmdui-class"></a>COleCmdUI 클래스
응용 프로그램의 `IOleCommandTarget`기반 기능과 관련된 사용자 인터페이스 개체의 상태를 업데이트하기 위한 MFC용 메서드를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|`COleCmdUI` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|설정 하거나 사용 명령 플래그를 지웁니다.|  
|[COleCmdUI::SetCheck](#setcheck)|켜기/끄기 전환의 상태를 설정 명령입니다.|  
|[COleCmdUI::SetText](#settext)|명령에 대 한 텍스트 이름 또는 상태 문자열을 반환합니다.|  
  
## <a name="remarks"></a>주의  
 사용할 수 없습니다. DocObjects, 사용자 응용 프로그램을 MFC 프로세스에서 메뉴를 볼 때 응용 프로그램에서 **UPDATE_COMMAND_UI** 통해 알림을 합니다. 각 알림에 제공 되는 [CCmdUI](../../mfc/reference/ccmdui-class.md) 특정 명령의 상태를 반영 하도록 조작할 수 있는 개체입니다. 그러나 DocObjects에 응용 프로그램을 사용할 때 MFC 처리 **UPDATE_OLE_COMMAND_UI** 알림 및 할당 `COleCmdUI` 개체입니다.  
  
 `COleCmdUI`컨테이너의 사용자 인터페이스 (예: FileNew, 열기, 인쇄 및 등)에서 발생 하는 명령을 수신 하도록 DocObject 있으며 컨테이너가 DocObject의 사용자 인터페이스에서 발생 하는 명령을 수신할 수 있도록 합니다. 하지만 `IDispatch` 발송 동일한 명령을 사용할 수 있습니다 `IOleCommandTarget` 쿼리 및 명령의 인수 없이 일반적으로 표준 집합에 의존 하므로 및 관련 된 형식 정보가 없기 때문에 실행 하는 간단한 방법을 제공 합니다. `COleCmdUI`사용 하도록 설정, 업데이트 및 사용자 인터페이스 명령 DocObject의 다른 속성을 설정할 데 사용할 수 있습니다. 명령을 호출 하는 경우 호출 [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)합니다.  
  
 참조에 대 한 자세한 내용은 DocObjects [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) 및 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)합니다. 또한 참조 [인터넷 첫 번째 단계: 활성 문서](../../mfc/active-documents-on-the-internet.md) 및 [액티브 문서](../../mfc/active-documents-on-the-internet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdocobj.h  
  
##  <a name="colecmdui"></a>COleCmdUI::COleCmdUI  
 생성 된 `COleCmdUI` 특정 사용자 인터페이스 명령과 연결 된 개체입니다.  
  
```  
COleCmdUI(
    OLECMD* rgCmds,  
    ULONG cCmds,  
    const GUID* m_pGroup);
```  
  
### <a name="parameters"></a>매개 변수  
 `rgCmds`  
 지정 된 GUID와 연관 된 지원 되는 명령의 목록입니다. **OLECMD** 구조 명령 플래그 명령에 연결 합니다.  
  
 *cCmds*  
 명령 수 `rgCmds`합니다.  
  
 `pGroup`  
 명령 집합을 식별 하는 GUID에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `COleCmdUI` 개체는 메뉴 항목, 컨트롤 막대 단추 등의 DocObject 사용자 인터페이스 개체를 업데이트 하기 위한 프로그래밍 인터페이스를 제공 합니다. 사용자 인터페이스 개체를 활성화, 비활성화,이 옵션을 선택 하거나 통해 선택이 취소 수 있습니다는 `COleCmdUI` 개체입니다.  
  
##  <a name="enable"></a>COleCmdUI::Enable  
 명령 플래그를 설정 하려면이 함수를 호출 하는 `COleCmdUI` 개체를 **OLECOMDF_ENABLED**를 가능 하 고, 활성화는 명령 인터페이스 알려줍니다 또는 명령 플래그를 지우려면.  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>매개 변수  
 `bOn`  
 와 연결 된 명령이 있는지 여부를 나타내는 `COleCmdUI` 개체를 활성화 또는 비활성화 해야 합니다. 0이 아니면 명령을; 활성화 0 명령을 사용 하지 않도록 설정 합니다.  
  
##  <a name="setcheck"></a>COleCmdUI::SetCheck  
 켜기/끄기 전환의 상태를 설정 하려면이 함수를 호출 명령입니다.  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCheck`  
 켜기/끄기 전환 설정할 상태를 결정 하는 값 명령입니다. 값:  
  
|값|설명|  
|-----------|-----------------|  
|**1**|이 명령은을 켜기로 설정합니다.|  
|**2**|비활성화 상태의;에 명령을 설정합니다 모두를 켜고 관련 선택 영역에 있는 상태에서이 명령의 특성은 이므로 상태를 확인할 수 없습니다.|  
|다른 모든 값|명령 off로 설정 합니다.|  
  
##  <a name="settext"></a>COleCmdUI::SetText  
 명령에 대 한 텍스트 이름 또는 상태 문자열을 반환 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 명령에 사용할 텍스트에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




