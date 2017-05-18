---
title: "COleLinkingDoc 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleLinkingDoc class
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: acdfde1413d5ff93efc63dbbf211881f71cf624e
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc 클래스
포함된 항목에 대한 연결을 지원하는 OLE 컨테이너 문서의 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|`COleLinkingDoc` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|OLE 시스템 Dll은 문서에 등록합니다.|  
|[COleLinkingDoc::Revoke](#revoke)|문서의 등록을 취소합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|지정 된 포함 된 항목을 찾습니다.|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|지정 된 연결 된 항목을 찾습니다.|  
  
## <a name="remarks"></a>주의  
 컨테이너 응용 프로그램을 지 원하는 포함 된 항목에 연결 "링크 컨테이너입니다." 라고 합니다. [OCLIENT](../../visual-cpp-samples.md) 샘플 응용 프로그램은 링크 컨테이너의 예입니다.  
  
 연결된 된 항목의 원본에 다른 문서에 포함된 된 항목 경우를 포함 하는 문서가 포함 된 항목을 편집할 수에 대 한 순서 대로 로드 되어야 합니다. 이러한 이유로 링크 컨테이너 연결된 된 항목의 원본을 편집 하는 사용자가 원하는 경우 다른 컨테이너 응용 프로그램에서 실행 될 수 있어야 합니다. 응용 프로그램 사용도 해야는 [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) 클래스를 프로그래밍 방식으로 시작 하는 경우 문서를 만들 수 있습니다.  
  
 컨테이너 링크 컨테이너를 하려면 문서에서 파생 `COleLinkingDoc` 대신 [COleDocument](../../mfc/reference/coledocument-class.md)합니다. 다른 OLE 컨테이너와 마찬가지로 응용 프로그램의 네이티브 데이터 뿐만 아니라 포함 또는 연결 된 항목을 저장 하기 위한 클래스를 디자인 해야 합니다. 또한 네이티브 데이터를 저장 하기 위한 데이터 구조를 디자인 해야 합니다. 정의 하는 경우는 `CDocItem`-응용 프로그램의 네이티브에 대 한 클래스를 파생 데이터를 정의한 인터페이스를 사용할 수 있습니다 `COleDocument` OLE 데이터 뿐만 아니라 기본 데이터를 저장할 수 있습니다.  
  
 응용 프로그램을 다른 컨테이너에 의해 프로그래밍 방식으로 실행할 수 있도록 선언는 `COleTemplateServer` 개체의 응용 프로그램의 구성원으로 `CWinApp`-클래스를 파생 합니다.  
  
 [!code-cpp[NVC_MFCOleContainer&23;](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 에 `InitInstance` 의 멤버 함수에 `CWinApp`-파생 클래스를 문서 서식 파일을 만들고 지정 여 `COleLinkingDoc`-문서 클래스와 파생:  
  
 [!code-cpp[NVC_MFCOleContainer #&24;](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 연결 프로그램 `COleTemplateServer` 개체는 개체를 호출 하 여 문서 서식 파일에 `ConnectTemplate` 멤버 함수와 OLE 시스템으로 호출 하 여 개체를 모든 클래스는 레지스터 **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer #&25;](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 샘플은 `CWinApp`-클래스 정의 파생 하 고 `InitInstance` 함수 OCLIENT를 참조 하십시오. H와 OCLIENT 합니다. MFC 샘플에서 CPP [OCLIENT](../../visual-cpp-samples.md)합니다.  
  
 사용 하 여 대 한 자세한 내용은 `COleLinkingDoc`, 문서를 참조 [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md) 및 [컨테이너: 고급 기능](../../mfc/containers-advanced-features.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="colelinkingdoc"></a>COleLinkingDoc::COleLinkingDoc  
 생성 된 `COleLinkingDoc` OLE 시스템 Dll와의 통신을 시작 하지 않고 개체입니다.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>주의  
 호출 해야는 `Register` 문서를 열면 OLE를 알리기 위해 멤버 함수입니다.  
  
##  <a name="onfindembeddeditem"></a>COleLinkingDoc::OnFindEmbeddedItem  
 문서에서 지정한 이름 가진 포함된 된 OLE 항목에 포함 되는지 여부를 결정 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszItemName`  
 요청 된 항목이 포함 된 OLE의 이름에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 항목;에 대 한 포인터 **NULL** 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 기본 구현 (이름 비교는 대/소문자 구분) 지정한 이름의 항목에 대 한 포함 된 항목의 목록을 검색 합니다. 사용자 고유의 메서드를 저장 하거나 포함 된 OLE 항목 이름을 지정 해야 하는 경우이 함수를 재정의 합니다.  
  
##  <a name="ongetlinkeditem"></a>COleLinkingDoc::OnGetLinkedItem  
 지정 된 이름의 연결 된 서버 항목을 문서에 포함 되는지 여부를 확인 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszItemName`  
 연결 된 OLE 요청한 항목의 이름에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 항목;에 대 한 포인터 **NULL** 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 기본 `COleLinkingDoc` 구현은 항상 **NULL**합니다. 이 함수는 파생된 클래스에서 재정의 된 `COleServerDoc` (이름 비교는 대/소문자 구분) 지정한 이름의 연결된 된 항목에 대 한 OLE 서버 항목의 목록을 검색할 수 있습니다. 저장 하거나 연결 된 서버 항목을 검색 하는 사용자 고유의 메서드를 구현한 경우이 함수를 재정의 합니다.  
  
##  <a name="register"></a>COleLinkingDoc::Register  
 문서를 열면 OLE 시스템 Dll에 알립니다.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>매개 변수  
 *pFactory*  
 OLE 팩터리 개체에 대 한 포인터 (수 **NULL**).  
  
 `lpszPathName`  
 컨테이너 문서의 정규화 된 경로에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 문서가 성공적으로 등록 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 만들거나 OLE 시스템 Dll에 문서를 등록 하는 명명 된 파일을 열 때이 함수를 호출 합니다. 문서는 포함 된 항목을 나타내는 경우이 함수를 호출할 필요가 없습니다 있습니다.  
  
 사용 중인 경우 `COleTemplateServer` 응용 프로그램에서 `Register` 에서 자동으로 호출 `COleLinkingDoc`의 구현의 `OnNewDocument`, `OnOpenDocument`, 및 `OnSaveDocument`합니다.  
  
##  <a name="revoke"></a>COleLinkingDoc::Revoke  
 문서를 열면 더 이상 OLE 시스템 Dll에 알립니다.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>주의  
 OLE 시스템 Dll으로 문서의 등록을 해지 하려면이 함수를 호출 합니다.  
  
 명명 된 파일을 닫을 때이 함수를 호출 해야 하지만 일반적으로 수행 필요 없습니다 직접 호출할 수 있습니다. `Revoke`자동으로 호출 `COleLinkingDoc`의 구현의 `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, 및 `OnSaveDocument`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [COleDocument 클래스](../../mfc/reference/coledocument-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)

