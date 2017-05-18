---
title: "CDocObjectServer 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServer class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 75fb0ba49d105a673e862ed3044e85ac9e990e9c
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserver-class"></a>CDocObjectServer 클래스
일반 `COleDocument` 서버를 전체 DocObject 서버로 만드는 데 필요한 추가 OLE 인터페이스( `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`, 및 `IPrint`)를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|`CDocObjectServer` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|문서 개체 서버를 활성화 하지만 표시 되지 않습니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|DocObject 보기를 표시합니다.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|DocObject 보기의 상태를 복원 합니다.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|DocObject 보기의 상태를 저장 합니다.|  
  
## <a name="remarks"></a>주의  
 `CDocObjectServer`파생 됩니다 `CCmdTarget` 와 밀접 하 게 호환 `COleServerDoc` 하는 인터페이스를 표시 합니다.  
  
 DocObject 서버 문서에 포함 될 수 있습니다 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 개체를 DocObject 항목에 대 한 서버 인터페이스를 나타냅니다.  
  
 DocObject 서버를 사용자 지정 하려면 사용자 고유의 클래스를 파생 `CDocObjectServer` 해당 보기 설정 함수를 재정의 하 고 [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), 및 [OnSaveViewState](#onsaveviewstate)합니다. 프레임 워크 호출에 대 한 응답에서 클래스의 새 인스턴스를 제공 해야 합니다.  
  
 참조에 대 한 자세한 내용은 DocObjects [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 및 [COleCmdUI](../../mfc/reference/colecmdui-class.md) 에 *MFC 참조*합니다. 또한 참조 [인터넷 첫 번째 단계: 활성 문서](../../mfc/active-documents-on-the-internet.md) 및 [액티브 문서](../../mfc/active-documents-on-the-internet.md)합니다.  
  
 또한 다음 기술 자료 문서를 참조 하십시오.  
  
-   Q247382: PRB: 도구 설명 컨트롤 ActiveX 문서 서버에 대 한 ActiveX 문서 컨테이너에 의해 숨겨집니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdocob.h  
  
##  <a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject  
 문서 개체 서버 활성화 (표시 하지는 않음)이이 함수를 호출 합니다.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>주의  
 `ActivateDocObject`호출 `IOleDocumentSite`의 **ActivateMe** 메서드를 설정 하 고 호출에 지정 된 보기를 표시 하는 방법에 대 한 지침이 될 때까지 대기 때문에 뷰를 표시 하지 않습니다 하지만 [CDocObjectServer::OnActivateView](#onactivateview)합니다.  
  
 함께 `ActivateDocObject` 및 `OnActivateView` 를 활성화 하 고 DocObject 보기를 표시 합니다. DocObject 활성화 다른 유형의 OLE 내부 활성화에서 다릅니다. DocObject 활성화 내부 해치 테두리 및 개체 도구 영역 (예: 크기 조정 핸들) 표시를 무시 하, 개체 범위 기능 무시 하 고, 스크롤 막대 (예: 기본 위치에서 활성화) 사각형 외부에 그리는 대신 보기 사각형을 그립니다.  
  
##  <a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer  
 `CDocObjectServer` 개체를 생성하고 초기화합니다.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pOwner*  
 DocObject 서버에 대 한 클라이언트는 클라이언트 사이트 문서에 대 한 포인터입니다.  
  
 `pDocSite`  
 에 대 한 포인터는 `IOleDocumentSite` 컨테이너에 의해 구현 된 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
 클라이언트 사이트 OLE 인터페이스 DocObject 활성화 되 면 ( `IOleDocumentSite`) DocObject 서버 (컨테이너) 클라이언트와 통신할 수 있습니다. DocObject 서버 활성화 되 면 먼저 확인 컨테이너가 구현 하는 `IOleDocumentSite` 인터페이스입니다. 그렇다면 [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) 컨테이너 DocObjects 지원 하는지 확인 하기 위해 호출 됩니다. 기본적으로 `GetDocObjectServer` 반환 **NULL**합니다. 재정의 해야 `COleServerDoc::GetDocObjectServer` 새 생성 하 `CDocObjectServer` 개체 또는 파생된 된 개체에 대 한 자체와 포인터는 `COleServerDoc` 컨테이너 및 해당 `IOleDocumentSite` 생성자에 인수로 인터페이스입니다.  
  
##  <a name="onactivateview"></a>CDocObjectServer::OnActivateView  
 DocObject 보기를 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>반환 값  
 오류 또는 경고 값을 반환합니다. 기본적으로 반환 **NOERROR** 성공 하 고, 그렇지 않으면 **E_FAIL**합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 내부 프레임 창을 만듭니다, 그리고 보기 내에서 스크롤 막대를 그립니다, 그리고 설정 하는 서버와 컨테이너의 공유, 프레임 컨트롤을 추가, 활성 개체를 설정 하는 다음 마지막으로 내부 프레임 창을 보여 줍니다 및 메뉴 포커스를 설정 합니다.  
  
##  <a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState  
 DocObject 보기의 상태를 복원 하려면이 함수를 재정의 합니다.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 `ar`  
 A `CArchive` 를 뷰 상태를 serialize 할 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 해당 인스턴스를 생성 한 후 처음으로 보기를 표시할 때 호출 됩니다. `OnApplyViewState`데이터에 따라 자체적으로 다시 초기화 하는 뷰를 지시는 `CArchive` 이전에 저장 된 개체 [OnSaveViewState](#onsaveviewstate)합니다. 보기에 있는 데이터의 유효성을 검사 해야는 `CArchive` 개체 컨테이너에 전혀 보기 상태 데이터를 해석 하려고 시도 하지 않습니다.  
  
 사용할 수 있습니다 `OnSaveViewState` 보기의 상태를 영구 정보를 저장 합니다. 재정의 하는 경우 `OnSaveViewState` 재정의 해야 할 정보를 저장 하기 위해 `OnApplyViewState` 해당 정보를 읽고, 새로 활성화 된 경우 보기에 적용 합니다.  
  
##  <a name="onsaveviewstate"></a>CDocObjectServer::OnSaveViewState  
 DocObject 보기에 대 한 추가 상태 정보를 저장 하려면이 함수를 재정의 합니다.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 `ar`  
 A `CArchive` 뷰 상태를 직렬화 할 개체입니다.  
  
### <a name="remarks"></a>주의  
 상태 보기 유형, 확대/축소 비율, 삽입 및 선택 지점 및 등과 같은 속성을 포함할 수 있습니다. 컨테이너는 일반적으로 보기를 비활성화 하기 전에이 함수를 호출 합니다. 통해 나중에 저장 된 상태를 복원할 수 [OnApplyViewState](#onapplyviewstate)합니다.  
  
 사용할 수 있습니다 `OnSaveViewState` 보기의 상태를 영구 정보를 저장 합니다. 재정의 하는 경우 `OnSaveViewState` 재정의 해야 할 정보를 저장 하기 위해 `OnApplyViewState` 해당 정보를 읽고, 새로 활성화 된 경우 보기에 적용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem 클래스](../../mfc/reference/cdocobjectserveritem-class.md)

